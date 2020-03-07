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


对于采用 MVC 架构的项目来说，其实最大的挑战在于维护 Controller。
而想要有良好维护的 Controller，最大的挑战又在于保持良好的测试覆盖。

> 这一点对于一些类似的其他架构也是一样的。比如 MVVM 或者 VIPER，广义上它们其实都是 MVC，
只不过使用 View Model 或者 Presenter 来做 Controller 而已。它们对应的控制器的职责依然是协调 Model 和 View。


## 传统 MVC 实现


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

