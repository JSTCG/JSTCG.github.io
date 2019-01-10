---
layout: post
title: Selenium Python
date: 2017-12-18 20:12:28.000000000 +08:00
tags: Selenium python
---

-----------------------------------------------

### 常见问题：
`什么是firefox的profile，profile有什么用？`[官方解释。][1]简单来说，profile保存了
>- 书签
>- 记住的password
>- 其他信息，比如cookie

webidrver启动浏览器的时候会产生临时的profile，这也是为什么每次浏览器启动以后我们都要重新登录系统的原因，profile重置了，登录态也就没保存下来了。
>我们在使用selenium做测试的时候可以指定使用1个已经存在的profile，从而实现一段时间的免登录功能。

[如何找到firefox的profile文件][2]
`如何在selenium中指定使用已存在的profile`
```Python
#传入profile所在的绝对路径
profile = webdriver.FirefoxProfile('/home/jmunsch/.mozilla/firefox/yxjwk1py.default')
driver = webdriver.Firefox(profile)
```
`Chrome headless 模式`

我们在通过Selenium运行自动化测试时，必须要启动浏览器，浏览器的启动与关闭必然会影响执行效率，而且还会干扰你做其它事情（本机运行的话）。
那能不能把自动化测试的运行放在后台？当然可以！
- htmlunit 项目可以模拟浏览器运行，是一个没有界面的浏览器，运行速度快。
- PhantomJS 是一个基于webkit的JavaScript API。它使用QtWebKit作为它核心浏览器的功能，使用webkit来编译解释执行JavaScript代码。任何你可以在基于webkit浏览器做的事情，它都能做到。
- Chrome-headless 模式，Google 自己出的无头浏览器模式。

htmlunit 在Selenium 下面，我都没跑通过一个 baidu 的 demo, 因为它不打开 UI 界面，所以，你也不知道它后台是如何渲染页面的。 弃之！

PhantomJS 非常不错，因为是使用的 QtWebKit 浏览器内核渲染页面，基本可以和真正浏览器保持一致。

Chrome-headless 模式， Google 针对 Chrome 浏览器新增加的一种模式，可以让你不打开UI界面的情况下使用 Chrome 浏览器，所以运行效果与 Chrome 保持完美一致。PhantomJS作者说，你这么搞我失业了啊！

用法

Python Selenium 用法:
```
from selenium import webdriver
from selenium.webdriver.chrome.options import Options

chrome_options = Options()
chrome_options.add_argument('--headless')
driver = webdriver.Chrome(chrome_options=chrome_options)
```
Java Selenium用法:
```
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;

public class WebTest {

    public static void main(String[] args) throws InterruptedException {

        ChromeOptions chromeOptions = new ChromeOptions();
        chromeOptions.addArguments("--headless");
        WebDriver driver = new ChromeDriver(chromeOptions);

        ...

    }
}
```


[1]:https://support.mozilla.org/en-US/kb/profiles-where-firefox-stores-user-data?redirectlocale=en-US&redirectslug=Profiles
[2]:https://support.mozilla.org/en-US/kb/profiles-where-firefox-stores-user-data?redirectlocale=en-US&redirectslug=Profiles#w_how-do-i-find-my-profile


-----------------------------------------------
