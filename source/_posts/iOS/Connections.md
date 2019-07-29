---
title: 四. 两个关联（Connections）
categories:
  - iOS
date: 2018-08-07 11:42:54
tags:
---

<!-- block -->

在本篇中我们详细解读一下iOS App开发的核心内容。
<!-- block -->

## 回顾

先回顾一下前面三篇你所学的内容：

1. 在“{% post_link Hello-World  开篇：Hello World %}”中你学会了打开Xcode创建一个iOS开发工程并在模拟器上运行了一个显示“Hello World”字样的最简单iOS App；
2. 在“{% post_link Make-it-Real 玩真的 %}”中你学会了把`Hello World`这个App安装到你的iPhone上运行。
3. 在“{% post_link Hello-World-2.0 让Hello World动起来 %}”中你学会了让你的`Hello World`动起来；


> Checkpoint: 此时你应该完成把App在模拟器和真机上都运行起来，你按那个按钮，屏幕上会弹出一个窗口了。

## 神奇操作

按钮被按下时那个窗口之所以会出现，是因为我们在{% post_link Hello-World-2.0 上一篇 %}中做了一个"神奇操作"：

{% qnimg connections/9.4.1/ctrldrag.gif %}

这个神奇操作在我们看到的界面（Main.storyboard文件）和iPhone内部运行的代码间建立了一个关联关系（Connection），其含义就是告诉iPhone当这个按钮被按下时，应该执行`showAlert()`这段代码。

{% qnimg connections/9.4.1/connectioninspector-annotated.png %}

当前你看到的这个关联关系的意思就是:当这个Button上发生了`Touch Up Inside`这个事件时触发`View Controller`中的`showAlert`（在工程中的ViewController.swift这个文件中的`showAlert()`函数）运行。

## 两层间的关联关系

这里需要**着重关注**一下，一个App内部实际上包含了两个层面的内容（后面我们会再进一步看到第三个层面）：我们在屏幕上看到的是一层，这一层里的内容就是在`Main.storyboard`文件中我们可以绘制的用户界面；还有一层是在你所看到的用户界面以下的，也就是`ViewController.swift`文件中写的代码。代码的运行是靠界面上用户界面上的操作驱动的，如下图所示。

{% qnimg connections/9.4.1/connection1.png %}

我们之前通过神奇操作做的事情就是在这两层间建立了一个Connection，让界面上的事件（Button的触碰）去驱动代码的执行（`showAlert()`）。

> Checkpoint: 理解这件事很重要。你理解了么？

在之前的{% post_link Hello-World-2.0 Hello World 2.0版 %}里，我们在`showAlert()`的代码里写了那段代码：

{% qnimg helloworld2.0/9.4.1/codeexplain.png %}

这段代码的意思就是在屏幕上显示一个警告窗口。如果现在当按钮被点到的时候我需要用户界面上的那个文字标签内容变化一下，应该怎么做呢？

### 调整关联

按之前的思路，我们应该写一段代码（也就是跟`showAlert()`类似的一个函数，我们可以管它叫`changeLabel()`），代码中执行修改Label内容的操作，然后让button的事件关联到这段新代码。如下图所示。

{% qnimg connections/9.4.1/connection-change.png %}

按此思路，我们先打开`ViewController.swift`这个文件，在原来写`showAlert()`的地方写上一个`changeLabel()`函数：

``` swift
@IBAction func changeLabel(){
    
}
```

然后跟之前一样，做个神奇操作。（记得要打开辅助编辑器哦，还记得怎么打开么？）

{% qnimg connections/9.4.1/newconnection.gif %}

这时你再选中`Button`后打开`Connection Inspector`会发现这个`Button`的`Touch Up Inside`事件关联到两个函数了。下面我们只需要按钮按下时去驱动`changeLabel()`执行，所以可以点那个小叉叉删掉不需要的那个关联关系。

{% qnimg connections/9.4.1/deleteconnection-annotated.png %}

动画演示如下：

{% qnimg connections/9.4.1/deleteconnection.gif %}

你可以在`changeLabel()`里写点简单的代码来测试一下是不是按钮按下后这个函数被执行了，例如可以这样：

``` swift
@IBAction func changeLabel(){
    print("changeLabel被执行")
}
```

新加的这一行`print("changeLabel被执行")`我相信你能理解。点击Xcode上的 ▶ 在iPhone或模拟器上运行，当你按`button`时Xcode底部会多出一块区域，现实代码的一些输出信息，如下图。

{% qnimg connections/9.4.1/output-annotated.png %}

## 第二类关联

下一个问题紧接着就来了，如何去改变那个文字标签的内容呢？我们如何能操作那个Label么？其实我们需要再来一个关联关系，让代码关联到界面上的某个元素，然后操作这个元素，如下图所示。

{% qnimg connections/9.4.1/connection-II.png %}


怎么做呢？还是那个神奇的操作，不过这次不是把`button`拖过来，而是把那个`label`拖过来。

{% qnimg connections/9.4.1/outletconnection.gif %}

如以上动画所示，我们在辅助编辑器模式下，在`Main.storyboard`里选中那个显示着`Hello World`文字的`Label`，然后按住键盘的`Ctrl`键用鼠标把这个Label拖到`ViewController.swift`编辑器的代码部分，当你鼠标拖动的时候，你会看到在某些位置出现一根蓝色提示线和提示文字`Insert Outlet or Outlet Connection`,这时就可以松开鼠标和`Ctrl`键，然后编辑器会弹出一个小窗口。

{% qnimg connections/9.4.1/outletdialog.png %}

在这个窗口中的`Name`字段填上一个字符串，例如`myLabel`然后点`Connect`。

这之后你会发现你的代码里多了一行：

``` swift
@IBOutlet weak var myLabel: UILabel!
```

`myLabel`称之为一个“变量”，这个概念我们在后面会详细解释，目前你可以把它理解为一个“抓手”，这个"抓手"让你可以操作界面上对应的那个文字标签，然后我们在`changeLabel()`这个函数中可以添加一行实际去操作文字标签：

``` swift
@IBAction func changeLabel(){
    print("changeLabel被执行")
    myLabel.text = "你好！"
}
```

`myLabel.text = "你好！"`意思是把`myLabel`的内容(`text`)设置为"你好“这个字符串。

点击Xcode上的 ▶ 在iPhone或模拟器上运行，当你按`button`时看看发生了什么？是不是像下面这个动画一样？

{% qnimg connections/9.4.1/run-hello.gif %}

## 理解两类关联关系

这个过程中的核心实际是就是我们所做的两次"神奇操作"

1. 我们把`Button`拖到`changeLabel()`函数上，让`Button`上发生的事件跟函数执行关联（**一号关联**）；
2. 我们把`Label`拖动到代码中生成了一个变量`myLabel`，这个变量关联（**二号关联**）到这个`Label`。

{% qnimg connections/9.4.1/IBActionOutlet.png %}

然后运行起来后，当我们触碰那个`Button`产生一个事件，根据前一个关联关系，系统知道要执行`changeLabel()`函数，这个函数运行中，去操作`myLabel`的内容（执行`myLabel.text = "你好！"`），根据第二个关联关系，系统知道`myLabel`指的是界面上那个文字标签，因此将那个标签设置为了新的内容。实际上你每次点文字标签的内容都在重新设置，只是每次都设置为一样的值，所以看起来只有第一次有效。我们也可以把这句话稍加改动变成这样。

``` swift
myLabel.text = "你好！" + String(arc4random_uniform(10))
```

这表示在"你好！”后面我们再拼接上一个随机的数字。`String(arc4random_uniform(10))`这个看不懂没有关系，到后面也许就懂了。

现在再运行。

{% qnimg connections/9.4.1/run-random.gif %}


## 小结

这一篇讲的内容很关键，是你理解iOS App开发的核心内容。为什么这么说呢？因为我们常用的iOS App就是你刚才完成的这个App的样子：

1. App运行，用户看到屏幕上出现一个界面；
2. 界面上某些地方用户是可以操作的，比如这个`Button`;
3. 用户触碰这个`Button`，系统产生事件；
4. 这个事件根据你开发App时定义的 **一号关联** ，驱动一段代码运行；
5. 代码运行中，将一些计算结果或者获得到的内容通过 **二号关联** 显示到界面上；
6. 用户看到界面上发生变化，进行下一次操作，产生下一个事件；
7. 新的事件可能又驱动另一段代码执行。如此往复。

这就叫**事件驱动的图形化应用程序**，掌握这个概念，你就算是程序员了。
