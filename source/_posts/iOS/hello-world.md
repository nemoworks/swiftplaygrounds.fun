---
title: 一. 开篇：Hello World
categories:
  - iOS
date: 2018-06-16 23:49:08
---

<!-- block -->

让我们先谈谈为什么要开始写这个网站。
<!-- block -->

# Apple和她的iOS

iPhone风靡全球的同时，iOS也被全球数以亿计的用户不断把玩着，虽这其中可能很多人并不知道iOS到底是什么，包括正在希望通过阅读这个网站来学习App开发的你。打个很老土的比方，若你买的iPhone比作一个人，那iOS就相当于这个人的大脑。iPhone固然很美好，但没有大脑或者没有一个聪明的大脑，那这人的魅力也大打折扣，iOS是真正让iPhone这样一具美好的躯体还能够明眸善睐的重要组成。

iOS虽然聪明，但原生的本事并不多。我们在iPhone上安装各种App来不务正业，比如发微信、看新闻、打游戏。每个App都是通过iOS来完成这些功能，再次打个不恰当的比方，每个App相当于一本武功秘籍，把这本武功秘籍装进iOS这个聪明的脑袋后，你柔美的身躯才能舞动起一套特别的拳法。我打的这些比方真的不是很合适，既俗套又不准确，我希望你看过后就忘记，等以后你自然会明白。

# 来此的目的

这个网站会写一些的内容告诉你怎么去为你的iOS开发各种武功秘籍指挥你的iPhone完成各种炫目功能。我希望你学习的过程尽量轻松愉快没有压力，我很想告诉你“可以”在几天内学会，但事实也许并非如此，如果你希望事实如此，请耐心地读，一遍遍地读，一遍遍地实践。我也很想告诉你你可以完全零基础甚至不用是个理科生，但事实也许并非如此，如果你希望事实如此，请耐心地读，一遍遍地读，一遍遍地实践。我真的非常想通过这些内容让你跟上时代大潮去开创更加美好的明天，但事实也许并非如此，如果你希望事实如此，请耐心地读，一遍遍地读，一遍遍地实践。

# 准备工作

首先你要有个iMac或者MacBook Pro，前者是台式电脑，后者是膝上型电脑（咱们中国人喜欢叫笔记本电脑）。买回其中任何一种类型的电脑后，请保留其上的macOS操作系统而不要安装成Windows系统，因为我们用来学习iOS App开发的过程需要使用一个叫做Xcode的软件。Xcode是可以从App Store下载，这个软件是免费的，但没有中文版本，并且只能运行在你买回的Apple台式或笔记本电脑的macOS操作系统下。怎么安装就不废话了，访问以下链接也能看到。

https://itunes.apple.com/us/app/xcode/id497799835?mt=12


尝试下载[这个文件](/scripts/activexcode.scpt)并运行。

这个软件的版本会不断更新，软件界面和操作方法也会不断变化。未来也许在你对照这个网站内容用这个软件的时候会发现两者并不完全一致，这很正常。我会尽量使之一致。

# Hello World

每一个码农都理解`Hello World`是个什么梗。你要是不知道的话看一下[Wikipedia](https://zh.wikipedia.org/wiki/Hello_World)上的解释。简单而言就是码农们学习一项新技能时完成的第一个最简单学习任务：让计算机说一句`Hello World`。我们学习iOS开发，当然也要落入俗套，来让iPhone跟你说一句`Hello World`。

1. 启动Xcode。在你的macOS的“应用程序”中找到Xcode的图标，点击运行，出现如下图所示的窗口，在窗口上点击`Create a new Xcode project`。

{% qnimg helloworld/9.4.1/startup-annotated.png %}

<!-- ![Xcode](/images/helloworld/9.4.1/startup-annotated.png) -->

2. 选择一个模板。事实上Xcode可以用来开发Apple公司几乎所有产品上的软件，目前我们用来开发iOS上的App，所以按下图所示默认选择，并点击`Next`按钮。

{% qnimg helloworld/9.4.1/template-annotated.png %}

<!-- ![项目模板](/images/helloworld/9.4.1/template-annotated.png) -->


3. 填写项目信息。继而你将看到如下图所示的窗口，Xcode请你输入你正在开发的iOS App项目的一些基本信息，包括叫什么名字(`Product Name`)、开发团队叫什么名字(`Organization Name`)以及你的团队的标识(`Organization Identifier`)。你可以就按图示填写，以后会慢慢解释具体含义。窗口上原来选中的`Include Unit Tests`和`Include UI Tests`也请去掉（不选择）。

{% qnimg helloworld/9.4.1/info-annotated.png %}

<!-- ![信息填写](/images/helloworld/9.4.1/info-annotated.png) -->

4. 选择保存地址。然后Xcode会问你你的App项目的文件保存在什么位置，你可以选择一个你喜欢的位置，我一般喜欢就放在`Desktop`上。然后请点`Create`按钮。

{% qnimg helloworld/9.4.1/save-annotated.png %}

<!-- ![保存地址](/images/helloworld/9.4.1/save-annotated.png) -->

5. 选择模拟器并启动。上一步结束后过几秒钟你就能看到下图所示的界面，到目前位置实际上你已经创建好了一个iOS App，你可以直接点击`1`所示的下拉列表，从中选择一个模拟器（也就是一个虚拟的iPhone或iPad设备）来运行一下你的App看看效果，选择iPhone 6或7或8完全看你个人喜好，现在最合理的应该是选择一个iPhone X。选好后你就可以点`2`所示的那个运行按钮。

{% qnimg helloworld/9.4.1/project-annotated.png %}

<!-- ![项目信息](/images/helloworld/9.4.1/project-annotated.png) -->

6. 模拟器运行。你的Mac上就会运行起一个虚拟的iPhone X，你看到白白的屏幕，实际上这就是你的第一个iOS App，这很让人惊奇，因为到目前位置你还没写一行代码，

{% qnimg helloworld/9.4.1/simulator-annotated.png %}

<!-- ![启动运行](/images/helloworld/9.4.1/simulator.png) -->

7. 在App的界面上添加文字。正是因为你确实什么都还没干，所以上面那个iPhone X中只有白白一片。现在我们在里面加点东西。先用鼠标在左边`1`所示选中那个`Main.storyboard`，然后点击`2`所示的那个如同铜钱一般的按钮，再在下面的列表中选中`3`所示的`Label`。选中后请直接用你的鼠标或者Trackpad拖动这个`Label`，放置到窗口中间那个矩形区域中。

{% qnimg helloworld/9.4.1/addlabel-annotated.png %}

<!-- ![添加文字标签](/images/helloworld/9.4.1/addlabel-annotated.png) -->

8. 修改文字内容。Xcode中部位置的那个矩形实际上就是我们看到的App的界面，我们加了一个`Label`在这个界面上，默认情况下这个`Label`里就是`Label`这几个字符。并我们双击一下它，然后可以修改这其中的文字。随便你写什么，仪式感一点的话，我们就写上`Hello World`。

{% qnimg helloworld/9.4.1/changetext-annotated.png %}

<!-- ![修改标签文字](/images/helloworld/9.4.1/changetext-annotated.png) -->

9. 运行看到`Hello World`。跟刚才一样，点击那个运行按钮。你看到你的App重新运行起来，屏幕上显示出让你热泪盈眶的`Hello World`。

{% qnimg helloworld/9.4.1/helloworld.png %}

<!-- ![Hello World](/images/helloworld/9.4.1/helloworld.png) -->

## 小结

1. 听了一些废话。
2. 安装了免费的Xcode，下定决心学习iOS App开发。
3. 按步骤开发出你的第一个iOS App：`Hello World` 。
  

## 🎉🎉🎉