---
title: 三. App原型设计
categories:
  - Project
date: 2019-07-22 10:59:49
---

### 明确功能需求

有了构思后，我们可以使用原型工具来做初步设计，把想法表达出来。这部分还是不需要写代码的，所以你不用害怕。

[上一篇](../App-Conception)中我们对App进行了构思，想好了App需要实现的几项功能，包括：

- 让用户记录当前行为：**每次用一次性产品产生垃圾时用App记下来**；
- 让用户对其历史数据查看：**用户可以看到以往任何一天自己产生的一次性物品垃圾清单**；
- 其他信息获取功能：**让用户接收查看来自某些网站上的环保主题文章**。

明确了这些后，我们就可以来进行原型设计了。


### 原型设计

原型设计的意思简单来说就是根据功能需求把实现这样功能的App界面、工作流程等描述出来，以便开发人员按你这个设计进行编程。除了用语言文字说出界面是什么样、App怎么工作之外，一般我们会通过画图的方式更形象地进行描述，这样的图就称为原型图。原型图可以用纸和笔来画，但工欲善其事必先利其器，你更应该学会使用专门来干这事的工具软件，这样的软件叫做原型工具。现在有很多工具可以使用，知乎上就有较为全面的[原型工具介绍](https://www.zhihu.com/question/19592829)。

我们使用[墨刀](https://modao.cc)来做这件事。对于小项目，墨刀使用是免费的。打开网站，注册用户，登陆，创建项目，此处不赘。

### 一个功能：记录

App的设计本身并不是信息领域的事儿，而是是设计领域的。一般大型的App会有专门的设计专业人士来完成设计过程。现在我们请不起专业人员来帮你做，那就自己动手做个简单的。

按照手机App的设计规范和原则，一般来说对于每一项给用户提供的功能，我们设计一个界面来让用户进行交互操作以实现这个功能。如果一个App就一项功能，比如你手机上的计算器，那就设计一个界面即可。当然一般而言App都有若干界面，类似淘宝这样的App甚至包括上百个界面。

我们首先考虑现在要设计的环保App的第一项功能--让用户记录当前行为，在脑中想象一下，怎么让用户记录呢？那肯定是让用户填写消耗了什么一次性产品，然后点个按钮“记录”，App将用户填的数据保存下来，记录功能就这样完成。所以界面上应该有若干输入框让用户输入你需要记录的信息，例如包括：时间、物品、数量甚至地点。你可以用墨刀画出下面这样一个界面原型图，有四个输入框，让用户可以输入哪天哪个时间段消耗了什么类型的什么一次性物品，在放个按钮让用户填完后点按钮保存。简单阀啦？

{% qnimg prototyping/first.png %}

App设计的另一个问题是，我们要考虑用户体验，也就是说让用户用起来尽量方便。比如日期时间段，一般默认情况下就是当前，所以后面在代码里面可以根据当前日期时间自动填入，用户需要的话再手工修改。这样简化了用户的操作，提升了用户体验。

App要做得好，那应该再深入想想，例如现在大城市开始施行垃圾分类，当你消耗了一次性物品后，要丢弃，丢的时候算哪类垃圾也是个灵魂拷问级别的问题，所以App设计时，可以考虑根据丢的东西帮用户判断是哪类，然后提示用户，因此可以在界面上这样设计：每次用户选定哪种东西后，自动提示类型。如下图。

{% qnimg prototyping/category.png %}

这样是不是更好一些？

### 其他功能

对于第二项功能，我们再设计第二个界面。让用户查看自己的数据可以用多种不同的界面实现，我们可以采用这样一个设计：在界面上放一个日历，用户可以选择一个日期，App加载所保存的这个日期的数据记录，然后在日历下方出一个列表，显示给用户看。如下图。

{% qnimg prototyping/calendar.png %}

同样，第三项功能在设计一个新界面，这个更简单（至少现在设计得非常简单），就一个列表，显示一系列环保文章的标题摘要，用户如果选择一个，进行新界面让用户看到具体内容。先画前面这个列表界面，后一个详细内容界面，你可以尝试自己画画看。

{% qnimg prototyping/news.png %}

一般而言，每个App还会有个“关于”界面，用于介绍App的一些信息。我们可以做一个简单设计，如下图。

{% qnimg prototyping/about.png %}

### 界面集成

这些功能的界面都一个个设计好了，怎么放在一起变成一个完整的App呢？这也有很多种方法，后面具体开发中会讲到。现在我们用简单的，因为这些功能都是相互独立的，所以我们可以用一个特殊的界面部件Tab把这些界面集成在一起。用户可以点击Tab上不同按钮调出不同界面来使用App的不同功能。如下图。

{% qnimg prototyping/tab.png %}


### TBC



