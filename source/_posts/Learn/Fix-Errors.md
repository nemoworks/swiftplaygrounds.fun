---
title: 五. 错误是不可避免的，但是不要重复错误
description: >-
  在你想到并开始学习iOS开发的时候，这件事给你的感觉是非常美好的，当你在读前面的几篇教程时你也会感觉良好，直到你真正掏出你精致的MacBook
  Pro开始按教程开发一个Hello
  World。突然间你发觉现实很残忍，因为Xcode很不听话地告诉你，有错误发生了。错误是不可避免的，解决错误是编程的一个重要环境。你经常听到码农说到“Debug”这个话题，Debug的意思就是解决程序中的错误，程序员一天的工作分成两部分：先花一小半时间写代码，再花一大半时间解决代码中的错误，这就是他们的日常。因此你目前这很正常，所以你遇到了错误也不用害怕。
categories:
  - Learn
date: 2018-08-26 14:16:58
---
<!-- block -->
错误是不可避免的，解决错误是编程的一个重要环节。
<!-- block -->

在你想到并开始学习iOS开发的时候，这件事给你的感觉是非常美好的，当你在读前面的几篇教程时你也会感觉良好，直到你真正掏出你精致的MacBook Pro开始按教程开发一个Hello World。突然间你发觉现实很残忍，因为Xcode很不听话地告诉你，有错误发生了。

你经常听到码农说到“Debug”这个话题，Debug的意思就是解决程序中的错误，程序员一天的工作分成两部分：先花一小半时间写代码，再花一大半时间解决代码中的错误，这就是他们的日常。因此你目前这很正常，所以你遇到了错误也不用害怕。

目前你会遇到这么几种错误，先分别说一下，如果你遇到的是别的，请联系我们，以便补充。

### 代码错误

实际上我们现在还没有正式在讲iOS App开发中用到的编程语言（Swift）的具体内容，所有的代码只要你照着抄就行，但即便这样你也很可能抄错。这样的错误发生时，你会发现在你点 ▶ 按钮想运行时Xcode给你一个错误提示显示在其顶部状态栏上，如下图：

{% qnimg fixerrors/9.4.1/errors-status.png %}

这行字告诉你Xcode在构造你的Hello World App时失败了（`Failed`），红色感叹号图标表示有错误发生，其右边的数字`1`代表发现的错误数是一项。当你点这个红色图标是，Xcode左侧导航栏会自动切换到第五页`Issue Navigator`（之前显示的是第一页`Project Navigator`）。这其中列出了Xcode帮你发现的错误，例如下图中Xcode告诉我们Swift Compiler发现一个错误（`Swift Compiler Error`）。Compiler是一个将我们写的代码翻译为计算机能理解并执行的代码的软件，中文叫做编译器，实际上目前我们开发软件所用的编程语言都是按我们人的思维方式和语言习惯来设计的，它们不是机器能直接理解的。`Swift Compiler Error`意思就是用来把Swift语言翻译为机器语言的编译器找到一个错误，错误具体是什么呢？是`Expected ')' in expression list`，也就是我们代码的某个位置缺少了一个括号。在我们用鼠标点（单击即可，双击的话Xcode会弹出一个新的编辑器窗口，你可以关闭这个新窗口）这行时，Xcode会定位到错误具体发生的位置，目前是`ViewController.swift`这个文件中的一行。

{% qnimg fixerrors/9.4.1/errors-positioning-annotated.png %}

仔细看一下代码

``` swift
self.present(alert, animated: true, completion: nil
```

这是我故意犯的一个错误，很明显这一行最后的`)`缺失了。Swift中的括号都是要成对的，无论是圆括号`()`还是花括号`{}`，具体后面再说，这样的错误我们只要补全括号就行。

``` swift
self.present(alert, animated: true, completion: nil)
```

你可能犯了类似的错误，仔细检查一下。

### 关系错乱

有时候你会发现点 ▶ 按钮运行时并没有错误，模拟器也启动了，但屏幕上白白的什么都没有，而Xcode也变为了这个样子：

{% qnimg fixerrors/9.4.1/errors-crash-annotated.png %}

这次Xcode实际上并没有告诉你哪行代码写错了，但你也不用着急，看一下下方输出窗口（Output）中的文字，当前显示：

``` 
...
libc++abi.dylib: terminating with uncaught exception of type NSException
(lldb) 
```

这看不懂是什么意思。没关系，往前翻至最顶部：

```
2018-08-26 15:20:59.802585+0800 HelloWorld[2797:394891] *** Terminating app due to uncaught exception 'NSUnknownKeyException', reason: '[<HelloWorld.ViewController 0x7f9af3903bf0> setValue:forUndefinedKey:]: this class is not key value coding-compliant for the key firstLabel.'
*** First throw call stack:
(
	0   CoreFoundation                      0x00000001112331e6 __exceptionPreprocess + 294
...

```

这对你来说当然也看不懂。不过其中包含了还是具有一定可读性的文字，例如第一行写道：`Terminating app due to uncaught exception 'NSUnknownKeyException'`，意思就是app被终止了，终止的原因是一个未被捕获的异常叫`NSUnknownKeyException`。Anyway，反正说的是app因为一个异常情况被终止了。

然后继续往后读：`reason: '[<HelloWorld.ViewController 0x7f9af3903bf0> setValue:forUndefinedKey:]: this class ...'`。这句应该是在解释原因，意思是`HelloWorld.ViewController`里面有错，特别是冒号后面写道：`this class is not key value coding-compliant for the key firstLabel`。这是什么意思？这句话的字面意思解释只能以后再展开，目前我们只能先说导致这个错误的原因，当你运行出错后在Output窗口看到Xcode报出`this class is not key value coding-compliant for the key XXX`这一的错误理由时，那说明你的App中存在错误的关联关系（Connection）。还记得Connection么？

{% qnimg connections/9.4.1/IBActionOutlet.png %}

关联关系哪里错了呢？我们需要来检查一下，看一下目前有哪些Connections。之前说了，打开`Main.storyboard`这个文件后在其用户界面上选中button或label组件后，右侧工具栏选择最后一个`Connection Inspector`可以看到这个组件的关联状态。

{% qnimg fixerrors/9.4.1/errors-inspector-annotated.png %}

上图显示这个button的`Touch Up Inside`事件关联到`changeLabel()`这个函数的执行。检查一下`ViewController.swift`代码文件，你发现这段代码确实存在。

{% qnimg fixerrors/9.4.1/errors-viewcontroller-annotated.png %}

继续检查，选中Label，看`Connection Inspector`


{% qnimg fixerrors/9.4.1/errors-iboutlet-annotated.png %}

我看到我的这个Label有两个Connections，分别关联到`myLabel`和`firstLabel`，检查一下`ViewController.swift`代码文件，你发现这段代码里只存在`myLabel`，而不存在`firstLabel`。

{% qnimg fixerrors/9.4.1/errors-viewcontroller-annotated2.png %}

至此我们找到了错误的原因：界面上那个Label建立的`firstLabel`关联在代码中消失了。修正这个错误很简单，只要点击那个Connection上的✖️即可。

{% qnimg fixerrors/9.4.1/errors-iboutlet-remove.png %}

第二种错误在初学时也经常会犯，且不那么容易被直接发现，产生的原因一般都是你在某个时刻通过那个魔法操作创建了一个界面元素与代码关联，但之后又在代码中删除了关联创建时新增的那行代码（后面我们会说，实际上这行代码表示一个变量的声明），你的App启动时，系统尝试把这个关联关系启用起来，发现代码中缺失了那一行，因此报错。

> 以上用`firstLabel`这个错误的关联举例介绍只是示意性地告诉你，你的app出`this class is not key value coding-compliant for the key XXX`这样的错误时应该怎么去找到错误。

类似的错误还可能有另一种形式，你可能也遇到了，我们尝试造出这个错误来：把`changeLabel()`这个函数删掉。注意，不是删一行，而是删掉这三行

``` swift
@IBAction func changeLabel(){
    myLabel.text = "你好！" + String(arc4random_uniform(10))
}
```

然后我们重写运行app，你会发现模拟器（或真机）将你的app启动起来，看似没有异常。但如果你按一下那个button，Xcode又一次报错，这时Output里出现的错误信息就跟刚才不太一样了：

```
018-08-26 16:32:47.194220+0800 HelloWorld[4475:613387] -[HelloWorld.ViewController changeLabel]: unrecognized selector sent to instance 0x7fe36aa080d0
2018-08-26 16:32:47.199959+0800 HelloWorld[4475:613387] *** Terminating app due to uncaught exception 'NSInvalidArgumentException', reason: '-[HelloWorld.ViewController changeLabel]: unrecognized selector sent to instance 0x7fe36aa080d0'
*** First throw call stack:
(
	0   CoreFoundation                      0x0000000107fc41e6 __exceptionPreprocess + 294
...
```

还是看其中的reason：`reason: '-[HelloWorld.ViewController changeLabel]: unrecognized selector sent to instance 0x7fe36aa080d0'`。这句话实际是在说“系统在尝试执行`changeLabel`时找不到这段代码了。为什么系统会去执行这段代码？因为用户按了button，而button有个关联关系，是去触发`changeLabel()`，可惜这段代码刚被我们删掉了，因此系统出错。这个错误刚app刚开始运行时是不会出现的，直到用户点击按钮这件事情发生。当然，目前这个错误发生是因为我们手工删除了那几行代码，你也许没故意删，但也发生了类似的错误，排除错误的方法跟上面一样，可以把button上的关联删除掉，这样在button被按时系统就什么都不做了，也就不会出错。如果你的button被按确实需要做事，你只是在某个时刻不小心删掉了代码，那就把代码重写出来，然后用我们之前的教程说的方法重新建立关联。


<!-- 还有一种方式，我们可以选中`View Controller`，然后在`Connection Inspector`中就能看到其以下的所有组件的关联关系。  -->

### 其他错误

App开发过程中实际上会遇到各种各样的错误发生，即使再有经验的程序员也不可能不犯错，不犯错的只有机器。所以你完全不用害怕出现了错误。

实际上我们也无法罗列所有错误及其解决方法，错误无处不在，比如在你运行前如果运行的目标设备选择错误（既不是某个模拟器也不是你的iPhone），Xcode也会报错。

{% qnimg fixerrors/9.4.1/errors-wrongdevice-annotated.png %}


遇到错误可以找人问，也可以在网上找答案。一个合格的程序员是必须通过网络找到自己需要的答案的，但请不要去问百度。除了Google外，一个叫StackOverflow的网站是码农必须知道的。在那里，你可以“Learn, Share, Build”。

https://stackoverflow.com/

Take care.


