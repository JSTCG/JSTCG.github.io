---
layout: post
current: post
cover:  assets/images/sky.jpg
navigation: True
title: 单向数据流动的函数式 View Controller
date: 2017-07-28 10:00:00
tags: tag-getting-started
class: post-template
subclass: 'post tag-getting-started'
author: ghost
---

View Controller 向来是 MVC (Model-View-View Controller) 中最让人头疼的一环，MVC 架构本身并不复杂，但开发者很容易将大量代码扔到用于协调 View 和 Model 的 Controller 中。

你不能说这是一种错误，因为 View Controller 所承担的本来就是胶水代码和业务逻辑的部分。但是，持续这样做必定将导致 Model View Controller 变成 Massive View Controller，代码也就一天天烂下去，直到没人敢碰。

对于采用 MVC 架构的项目来说，其实最大的挑战在于维护 Controller。而想要有良好维护的 Controller，最大的挑战又在于保持良好的测试覆盖。因为往往 View Controller 中会包含很多状态，而且会有不少异步操作和用户触发的事件，所以测试 Controller 从来都不是一件简单的事情。

> 这一点对于一些类似的其他架构也是一样的。比如 MVVM 或者 VIPER，广义上它们其实都是 MVC，只不过使用 View Model 或者 Presenter 来做 Controller 而已。它们对应的控制器的职责依然是协调 Model 和 View。

在这篇文章里，我会先实现一个很常见的 MVC 架构，然后对状态和状态改变的部分进行抽象及重构，最终得到一个纯函数式的易于测试的 View Controller 类。希望通过这个例子，能够给你在日常维护 View Controller 的工作中带来一些启示或者帮助。

如果你对 React 和 Redux 有所了解的话，文中的一些方法可能你会很熟悉。不过即使你不了解它们，也并不会妨碍你理解本文。我不会去细究概念上的东西，而会从一个大家都所熟知的例子开始进行介绍，所以完全不用担心。你可能需要对 Swift 有一些了解，本文会涉及一些基本的值类型和引用类型的区别，如果你对此不是很明白的话，可以参看一些其他资料，比如我以前写的[这篇文章](http://swifter.tips/value-reference/)。

整个示例项目我放在了 [GitHub](https://github.com/onevcat/ToDoDemo) 上，你可以在各个分支中找到对应的项目源码。

## 传统 MVC 实现

我们用一个经典的 ToDo 应用作为示例。这个项目可以从网络加载待办事项，我们通过输入文本进行添加，或者点击对应条目进行删除：

<center>
<video width="272" height="480" controls>
  <source src="/assets/images/2017/todo-video.mp4" type="video/mp4">
</video>
</center>

注意几个细节：

1. 打开应用后加载已有待办列表时花费了一些时间，一般来说，我们会从网络请求进行加载，这应该是一个异步操作。在示例项目里，我们不会真的去进行网络请求，而是使用一个本地存储来模拟这个过程。
2. 标题栏的数字表示当前已有的待办项目，随着待办的增减，这个数字会相应变化。
3. 可以使用第一个 cell 输入，并用右上角的加号添加一个待办。我们希望待办事项的标题长度至少为三个字符，在不满足长度的时候，添加按钮不可用。

实现这些并没有太大难度，一个刚入门 iOS 的新人也应该能毫无压力搞定。我们先来实现模拟异步获取已有待办的部分。新建一个文件 ToDoStore.swift:

```swift
import Foundation

let dummy = [
    "Buy the milk",
    "Take my dog",
    "Rent a car"
]

struct ToDoStore {
    static let shared = ToDoStore()
    func getToDoItems(completionHandler: (([String]) -> Void)?) {
        DispatchQueue.main.asyncAfter(deadline: .now() + 2) {
            completionHandler?(dummy)
        }
    }
}
```

为了简明，我们使用简单的 `String` 来代表一条待办。这里我们等待了两秒后才调用回调，传回一组预先定义的待办事项。

由于整个界面就是一个 Table View，所以我们创建一个 `UITableViewController` 子类来实现需求。在 TableViewController.swift 中，我们定义一个属性 `todos` 来存放需要显示在列表中的待办事项，然后在 `viewDidLoad` 里从 `ToDoStore` 中进行加载并刷新 `tableView`：

```swift
class TableViewController: UITableViewController {

    var todos: [String] = []

    override func viewDidLoad() {
        super.viewDidLoad()

        ToDoStore.shared.getToDoItems { (data) in
            self.todos += data
            self.title = "TODO - (\(self.todos.count))"
            self.tableView.reloadData()
        }
    }
}
```

当然，我们现在需要提供 `UITableViewDataSource` 的相关方法。首先，我们的 Table View 有两个 section，一个负责输入新的待办，另一个负责展示现有的条目。为了让代码清晰表意自解释，我选择在 `TableViewController` 里内嵌一个 `Section` 枚举：

```swift
class TableViewController: UITableViewController {
    enum Section: Int {
        case input = 0, todos, max
    }

    //...
}
```

这样，我们就可以实现 `UITableViewDataSource` 所需要的方法了：

```swift
class TableViewController: UITableViewController {
    override func numberOfSections(in tableView: UITableView) -> Int {
        return Section.max.rawValue
    }

    override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        guard let section = Section(rawValue: section) else {
            fatalError()
        }
        switch section {
        case .input: return 1
        case .todos: return todos.count
        case .max: fatalError()
        }
    }

    override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        guard let section = Section(rawValue: indexPath.section) else {
            fatalError()
        }

        switch section {
        case .input:
            // 返回 input cell
        case .todos:
            // 返回 todo item cell
            let cell = tableView.dequeueReusableCell(withIdentifier: todoCellResueId, for: indexPath)
            cell.textLabel?.text = todos[indexPath.row]
            return cell
        default:
            fatalError()
        }
    }
}
```

`.todos` 的情况下很简单，我们就用标准的 `UITableViewCell` 就好。对于 `.input` 的情况，我们需要在 cell 里嵌一个 `UITextField`，并且要在其中的文本改变时能告知 `TableViewController`。我们可以使用传统的 delegate 的模式来实现，下面是 TableViewInputCell.swift 的内容：

```swift
protocol TableViewInputCellDelegate: class {
    func inputChanged(cell: TableViewInputCell, text: String)
}

class TableViewInputCell: UITableViewCell {
    weak var delegate: TableViewInputCellDelegate?
    @IBOutlet weak var textField: UITextField!

    @objc @IBAction func textFieldValueChanged(_ sender: UITextField) {
        delegate?.inputChanged(cell: self, text: sender.text ?? "")
    }
}
```

我们在 Storyboard 中创建对应的 table view 和这个 cell，然后将其中的 text field 的 `.editingChanged` 事件绑到 `textFieldValueChanged` 上。每次当用户进行输入时，`delegate` 的方法将被调用。

在 `TableViewController` 里，现在可以返回 `.input` 的 cell，并设置对应的代理方法来更新添加按钮了：

```swift

class TableViewController: UITableViewController {
    override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        guard let section = Section(rawValue: indexPath.section) else {
            fatalError()
        }

        switch section {
        case .input:
            let cell = tableView.dequeueReusableCell(withIdentifier: inputCellReuseId, for: indexPath) as! TableViewInputCell
            cell.delegate = self
            return cell
        //...
        }
    }
}

extension TableViewController: TableViewInputCellDelegate {
    func inputChanged(cell: TableViewInputCell, text: String) {
        let isItemLengthEnough = text.count >= 3
        navigationItem.rightBarButtonItem?.isEnabled = isItemLengthEnough
    }
}
```

现在，运行程序后等待一段时间，读入的待办事项就可以被展示了。接下来，添加待办和移除待办的部分很容易实现：

```swift
class TableViewController: UITableViewController {
    // 添加待办
    @IBAction func addButtonPressed(_ sender: Any) {
        let inputIndexPath = IndexPath(row: 0, section: Section.input.rawValue)
        guard let inputCell = tableView.cellForRow(at: inputIndexPath) as? TableViewInputCell,
              let text = inputCell.textField.text else
        {
            return
        }
        todos.insert(text, at: 0)
        inputCell.textField.text = ""
        title = "TODO - (\(todos.count))"
        tableView.reloadData()
    }

    // 移除待办
    override func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
        guard indexPath.section == Section.todos.rawValue else {
            return
        }

        todos.remove(at: indexPath.row)
        title = "TODO - (\(todos.count))"
        tableView.reloadData()
    }
}
```

> 为了保持简单，这里我们直接 `tableView.reloadData()` 了，讲道理的话更好的选择是只针对变动的部分做 `insert` 或者 `remove`，但为了简单起见，我们就直接重载整个 table view 了。

好了，这是一个非常简单的一百行都不到的 View Controller，可能也是我们每天都会写的代码，所以我们就不吹捧这样的代码“条理清晰”或者“简洁明了”了，你我都知道这只是在 View Controller 规模尚小时的假象而已。让我们直接来看看潜在的问题：

1. UI 相关的代码散落各处 - 重载 `tableView` 和设置 `title` 的代码出现了三次，设置右上 button 的 `isEnabled` 的代码存在于 extension 中，添加新项目时我们先获取了输入的 cell，然后再读取 cell 中的文本。这些散落在各处的 UI 操作将会成为隐患，因为你可能在代码的任意部分操作这些 UI，而它们的状态将随着代码的复杂变得“飘忽不定”。
2. 因为 1 的状态复杂，使得 View Controller 难以测试 - 举个例子，如果你想测试 `title` 的文字正确，你可能需要手动向列表里添加一个待办事项，这涉及到调用 `addButtonPressed`，而这个方法需要读取 `inputCell` 的文本，那么你可能还需要先去设置这个 cell 中 `UITextField` 的 `text` 值。当然你也可以用依赖注入的方式给 `add` 方法一个文本参数，或者将 `todos.insert` 和之后的内容提取成一个新的方法，但是无论怎么样，对于 model 的操作和对于 UI 的更新都没有分离 (因为毕竟我们写的就是“胶水代码”)。这正是你觉得 View Controller 难以测试的最主要原因。
3. 因为 2 的难以测试，最后让 View Controller 难以重构 - 状态和 UI 复杂度的增加往往会导致多个 UI 操作维护着同一个变量，或者多个状态变量去更新同一个 UI 元素。不论是哪种情况，都让测试变得几乎不可能，也会让后续的开发人员 (其实往往就是你自己！) 在面对复杂情况下难以正确地继续开发。Massive View Controller 最终的结果常常是牵一发而动全身，一个微小的改动可能都需要花费大量的时间进行验证，而且还没有人敢拍胸脯保证正确性。这会让项目逐渐陷入泥潭。

这些问题最终导致，这样一个 View Controller 难以 scaling。在逐渐被代码填满到一两千行时，这个 View Controller 将彻底“死去”，对它的维护和更改会困难重重。

> 你可以在 GitHub repo 的 [basic 分支](https://github.com/onevcat/ToDoDemo/tree/basic)找到对应这部分的代码。
