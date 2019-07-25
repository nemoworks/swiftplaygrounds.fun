---
title: 二. 玩真的
date: 2018-06-24 21:44:35
tags:
description: 现在你的`HelloWorld`能在模拟器里运行了，你也肯定不满足于此。你希望玩真的。
category: Learn


---
<!-- block -->

现在你的`HelloWorld`能在模拟器里运行了，你也肯定不满足于此。你希望玩真的。
<!-- block -->

我们所用的Xcode不仅仅能在模拟器里运行你的App，它还可以将App直接在iOS真机上运行起来。除了一些特别老旧的型号之外，基本上所有的iPhone/iPad/iPod touch都可以用来运行你的App，具体而言所支持的型号就是在我们之前选择模拟器的那个列表中列出的型号。

{% qnimg makeitreal/9.4.1/simulators.png %}

<!-- ![simulators](/images/makeitreal/9.4.1/simulators.png) -->



除了得花点钱备置个iOS设备，你还需要有一个Apple开发者账号。如果你之前用过Apple的产品，比如iPhone或iPad，那一定在Apple注册过一个账号，叫做`Apple ID`，用这个账号你可以从App Store下载各类App。如果你没有注册过Apple ID，你可以访问<https://appleid.apple.com/>这个网站免费注册一个。有了这个`Apple ID`的基础之上，你再向Apple申请一下，说“兄弟我想当个码农给你Apple开发点App赚点钱”，然后Apple会给你一些服务和资源，让你成为一个“开发者”。具体过程非常简单，打开你的浏览器访问<https://developer.apple.com>，在以下页面右上角点击`Account`。

{% qnimg makeitreal/9.4.1/developer.apple-annotated.png %}

<!-- ![developer.apple.com](/images/makeitreal/9.4.1/developer.apple-annotated.png) -->



然后用你的`Apple ID`在下面这个页面上登录即可。如果没有`Apple ID`，也可以在此点击`Create Apple ID`按钮创建一个。

{% qnimg makeitreal/9.4.1/login.png %}

<!-- ![login](/images/makeitreal/9.4.1/login.png) -->


正常的话你登录后会进入下一页，看到Apple要你同意一个开发者协议，点同意即可。你也别无选择。


我们在开篇时创建了第一个Hello World工程后，你在Xcode左侧选择顶层带有蓝色图标的`HelloWorld`时能看到以下画面。

{% qnimg makeitreal/9.4.1/team-annotated.png %}

<!-- ![team](/images/makeitreal/9.4.1/team-annotated.png) -->



细心的你也许之前会发现，这个界面中间存在一个红色感叹号。一般看到感叹号就说明存在问题或错误，当前界面上的感叹号说的是我们这个工程没有设置一个开发团队来为这个App进行“签名”。“签名”这个词是密码学中的一个名词，用一个文科生能理解的说法来解释的话，所谓的为一个App签名，相当于为App打上个烙印，说明这个App作者是你，并且别人无法伪造你的烙印。每一个App都需要这么个烙印，成为开发者的意义实际上在于Apple公司为你生成一块独一无二的烙铁，你可以拿这块烙铁去炮烙你所开发的App。

在此，你需要告诉Xcode你从Apple拿到的烙铁是什么样的，这个过程在三五年前很挺复杂的，但现在的新版Xcode让此简单了很多，只要在上图所示界面上点`Add Account...`，然后输入你注册的Apple开发者账号即可。

{% qnimg makeitreal/9.4.1/addaccount.png %}

<!-- ![添加账号](/images/makeitreal/9.4.1/addaccount.png) -->

输入账号和密码后点`Next`，能看到你添加了一个`Personal Team`类型的账号。

{% qnimg makeitreal/9.4.1/accounts-annotated.png %}


<!-- ![Personal Team](/images/makeitreal/9.4.1/accounts-annotated.png) -->

`Personal Team`类型的意思就是你一个人单干，并且实际上是免费的。用这个账号你可以把你的App运行在你自己的iOS设备上进行开发，但不能将App发布到App Store上去供其他人免费下载或购买。如果以后你觉得自己开发的App足够好可以放到App Store上去，那可以在Apple Developer网站上注册一个Developer Program，每年交99美元即可。这是后话。


Okay，加完账号以后关闭当前对话框回到工程信息那页，你就可以在`Team`那边选择你刚加的那个`Personal Team`了。

{% qnimg makeitreal/9.4.1/team-selection.png %}


<!-- ![team-selection](/images/makeitreal/9.4.1/team-selection.png) -->

不过这样选择以后你会发现在`Team`下面有一大段红色提示文字，说明还存在错误。其中有个`Fix Again`按钮。

{% qnimg makeitreal/9.4.1/fixagain-annotated.png %}


<!-- ![fixagain](/images/makeitreal/9.4.1/fixagain-annotated.png) -->


出现这个错误是因为你没有告诉Apple你用来开发的iOS设备是哪个，如前所说，这背后的事情其实挺复杂，我们就先不解释了。解决的方法很简单，把你的iOS设备（iPhone或者iPad或者iPod）用线连接到你的mac上（如果之前没有连过，mac会提示是不是要访问这个设备上的信息，iOS设备也会问你是不是要信任你的mac，诸如此类，请都作肯定性选择，以连通你的mac和iOS设备），在之前我们选择模拟器的那个列表里你就能看到你的iOS设备名字也会出现在其中，选择它。

{% qnimg makeitreal/9.4.1/realdevice-annotated.png %}


<!-- ![realdevice](/images/makeitreal/9.4.1/realdevice-annotated.png) -->

我在连接的是一台名字叫`ECC's iPod`的设备。选择之后刚才红色错误信息的位置会更新，变成大概如下样子

{% qnimg makeitreal/9.4.1/fixed.png %}

<!-- ![fixed](/images/makeitreal/9.4.1/fixed.png) -->

这时你就可以再点运行按钮▶。你的mac可能会弹出一个对话框，如下。

{% qnimg makeitreal/9.4.1/keychain.png %}

<!-- ![keychain](/images/makeitreal/9.4.1/keychain.png) -->

输入你当前mac上的登陆密码即可。然后，你会发现Xcode还是告诉你有错误，会出现一个如下的对话框。

{% qnimg makeitreal/9.4.1/cannotlaunch-annotated.png %}

<!-- ![keychain](/images/makeitreal/9.4.1/cannotlaunch-annotated.png) -->

这个错误提示你说你的App还不能在你的iOS设备上允许，你还需要在iOS设备进系统设置去对在这台设备上运行你开发的App进行确认。

打开你的iOS设备（为了避免拗口，后面假设你用的是iPhone），你会发现其实你的iPhone上已经多了一个App的图标，名字叫`HelloWorld`。

{% qnimg makeitreal/9.4.1/app.png %}


<!-- ![app](/images/makeitreal/9.4.1/app.png) -->

在能运行它之前，我们在iPhone上需要进入`设置`的`通用`那一页，往下翻，找到`设备管理`

{% qnimg makeitreal/9.4.1/devicemgr-annotated.png %}

<!-- ![设备管理](/images/makeitreal/9.4.1/devicemgr-annotated.png) -->

进入`设备管理`后点击你刚才的开发者账号那一项

{% qnimg makeitreal/9.4.1/devapp-annotated.png %}

<!-- ![开发者应用](/images/makeitreal/9.4.1/devapp-annotated.png) -->

选择信任你的账号

{% qnimg makeitreal/9.4.1/trust-annotated.png %}

<!-- ![信任](/images/makeitreal/9.4.1/trust-annotated.png) -->

并确认

{% qnimg makeitreal/9.4.1/confirm.png %}

<!-- ![确认](/images/makeitreal/9.4.1/confirm.png) -->

然后，我们重新回到Xcode，再次运行。

如果你在你的iPhone上看到自动启动了一个App，并出现这个App的运行结果，那就恭喜你了。🎉🎉🎉

<!-- ![iPhone上运行](/images/makeitreal/9.4.1/rerun.jpg) -->

{% qnimg makeitreal/9.4.1/rerun.jpg %}

如果没有成功，那联系我们。

<ecc@idup.club>







