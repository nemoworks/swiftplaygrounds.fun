---
title: 三. 让Hello World动起来
date: 2018-07-02 22:49:08
tags:
description: HelloWorld这个App似乎过于简单了，不是么？好歹应该能跟用户互动一下，不是么？Okay，我们接着来做一个升级版本。
category: Learn

---

<!-- block -->

上一篇中的`Hello World`应不存在任何难度，文科生都能顺利完成。但这个App似乎过于简单了，不是么？好歹应该能跟用户互动一下，不是么？Okay，我们接着来做一个升级版本。
<!-- block -->

你肯定已经关闭了你的Xcode，现在重现运行起来，在之前选择`Create a new Xcode project`的启动窗口右边是最近你打开过的Xcode项目列表，这个列表中应该有你的`Hello World`，点击打开这个项目。

{% qnimg helloworld2.0/9.4.1/open-annotated.png %}

<!-- ![打开](/images/helloworld2.0/9.4.1/open-annotated.png) -->



当然，你也可以在macOS的Finder应用中找到你之前保存你的`Hello World`工程的文件夹然后双击`HelloWorld.xcodeproj`这个文件（其实它不是个文件，也是个文件夹，在macOS中叫做一个bundle，这个后面再详细说）。

{% qnimg helloworld2.0/9.4.1/finder-annotated.png %}

<!-- ![finder](/images/helloworld2.0/9.4.1/finder-annotated.png) -->


刚才说了，我们希望至少这个iOS app是能跟用户互动起来的，要做到这一点，我们接下来做三件事。这三件事以后会反复做，这是让你成为一个能写iOS App的高手的第一招，所以你要学会。

1. 在界面上添加能引起互动的元素
2. 写一点代码告诉系统互动的内容
3. 连接界面元素和代码建立互动关系

当然，现在直接说要做这三件事你可能并不明白其中的含义。我们一件件来。

### 在界面上添加能引起互动的元素

打开工程后，跟上次添加那个文字标签（`Label`）很类似，先用鼠标在左边`1`所示选中那个`Main.storyboard`，然后点击`2`所示的那个如同铜钱一般的按钮，再在下面的列表中选中`3`所示的`Button`（这个列表其实很长，你需要滚动找到这个`Button`）。然后如第4步所示，选中后请直接用你的鼠标或者Trackpad拖动这个`Button`，放置到窗口中间那个矩形区域中。

{% qnimg helloworld2.0/9.4.1/addbutton-annotated.png %}


<!-- ![添加一个按钮](/images/helloworld2.0/9.4.1/addbutton-annotated.png) -->



点击那个显示图标 ▶ 的运行按钮，你会看到模拟器启动，看到你的App又一次运行起来，屏幕上显示出`Hello World`，文字下面有个`Button`字样的按钮。这个按钮你可以用鼠标或Trackpad去点击，但没有任何反应。这不奇怪，因为你还没告诉iOS，这个按钮点了有导致什么后果😨。

### 写一点代码告诉系统互动的内容

在Xcode左侧选中`1`所示那个`ViewController.swift`文件，在Xcode中间区域（编辑区）的`2`所示位置敲入代码（恭喜你第一次真正在写iOS App代码）。如下图所示。

{% qnimg helloworld2.0/9.4.1/typecode-annotated.png %}


<!-- ![敲代码](/images/helloworld2.0/9.4.1/typecode-annotated.png) -->


我知道你可能从未写过代码，也看不懂这些天书的意思，没关系，照着抄就行。也许你视力不好看不清图片上的文字，没关系，我把文字放在下面，直接复制粘贴也行。

```swift
    @IBAction func showAlert(){
        let alert = UIAlertController(title: "警告", message: "⚠️皇上，您的按钮被点啦！", preferredStyle: .alert)
        alert.addAction(UIAlertAction(title: "朕知道了", style: .default, handler: nil))
        self.present(alert, animated: true, completion: nil)
    }
```
看，代码多美。编程多美。

简单解释一下这些天书：

{% qnimg helloworld2.0/9.4.1/codeexplain.png %}

<!-- ![天书奇谈](/images/helloworld2.0/9.4.1/codeexplain.png) -->




### 连接界面元素和代码建立互动关系

在Xcode的右上角有个“双环”按钮，如下图中`1`所示，点击后你原来的编辑器会裂变为两个编辑区。我们一般把右边那个新出来的叫"辅助编辑器"。副主编辑器和原来那个（称为主编辑器）可以分别显示两个文件的内容。

{% qnimg helloworld2.0/9.4.1/assistanteditor-annotated.png %}


<!-- ![副主编辑器](/images/helloworld2.0/9.4.1/assistanteditor-annotated.png) -->

点击`2`位置的另一个双环图标，会出来一个选择列表，按下图所示一路选择

{% qnimg helloworld2.0/9.4.1/selection1-annotated.png %}


<!-- ![选择storyboard文件](/images/helloworld2.0/9.4.1/selection1-annotated.png) -->

再按下图所示一路选择，直至最终选择到`Main.storyboard(Base)`这个文件。

{% qnimg helloworld2.0/9.4.1/selection2-annotated.png %}


<!-- ![选择storyboard文件](/images/helloworld2.0/9.4.1/selection2-annotated.png) -->

这时你的副主编辑器会变了模样，看到那个`B`图标后面跟着（`Button`）字样的那个，选中它（不要双击，单击即可），然后按住键盘上的`Control`键，将它拖动到左边主编辑器（这时应该显示的是那个`ViewController.swift`文件的内容）的那块你刚才敲入的新代码区域。如下图所示。

{% qnimg helloworld2.0/9.4.1/connect-annotated.png %}


<!-- ![建立Connection](/images/helloworld2.0/9.4.1/connect-annotated.png) -->

这时候你会看到整个新敲入的那块代码会被加亮，屏幕上会显示`Connect Action`整个标签。Okay，如果这样，你可以松开键盘和鼠标。

好了，我们再点击 ▶ 按钮。运行结果应该是这样的：


{% qnimg helloworld2.0/9.4.1/run.png %}

<!-- ![运行](/images/helloworld2.0/9.4.1/run.png) -->

模拟器里显示`Hello World`，文字下面有个`Button`，你点击一下它试试，是不是看到这样？

{% qnimg helloworld2.0/9.4.1/alert.png %}


<!-- ![运行](/images/helloworld2.0/9.4.1/alert.png) -->


如果是的话，那就是你的App对你的动作有了回应了。

### 再回顾一下

我们做了三件事：


1. 在界面上添加能引起互动的元素
2. 写一点代码告诉系统互动的内容
3. 连接界面元素和代码建立互动关系

这三件事实际上做了什么呢？看一下下面的解释。你能理解么？

{% qnimg helloworld2.0/9.4.1/explain.png %}

<!-- ![运行原理解释](/images/makeitreal/9.4.1/explain.png) -->


<!-- ![运行](/images/helloworld2.0/9.4.1/explain.png) -->


### 🎉🎉🎉


这时你可以再次把你的iPhone接上，让你的新版Hello World运行在它上面。