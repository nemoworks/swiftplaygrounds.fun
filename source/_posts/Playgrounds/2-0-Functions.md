---
title: 第二部分 函数 (Functions)
categories:
  - Playgrounds
date: 2016-07-25 22:16:06
---


每天我们都做很多事情，比如刷牙、吃早餐、系鞋带... 这其中每件事情要完成都需要多个步骤，拿系鞋带来说，我们先要把鞋带打成环（loop），然后交叉（swoop），最后收紧(pull)。

 {% qnimg playgrounds/functions/introduction/1s.png title:绑鞋带步骤 alt:绑鞋带步骤 %}

<!-- ![绑鞋带步骤](/images/functions/introduction/1s.png) -->


换成计算机的语言，绑鞋带这个任务就是要执行三个命令，分别为`loop()`、`swoop()`和`pull()`，把这三个步骤合在一起并取个名字例如“绑鞋带”(tieMyShoe)，就可以定义一个函数(Function)。换而言之定义一个函数就是用简单指令合成了一个更加复杂的指令，用代码表示就是下面所示的样子：

```Swift
func tieMyShoe(){
	loop()
	swoop()
	pull()
}
```

其中`func`代表现在我们自己定义一个函数，名称为`tieMyShoe`，每个函数名称后面都需要跟上一对圆括号`()`，然后用一对花括号`{}`把实现这个复杂任务的一个个简单步骤按顺序放在其中。这样定义完后，它就可以被当作一个指令来用，就跟你之前使用的`moveForward()`、`turnLeft()`和`collectGem()`是一样的。发出`tieMyShoe()`这个指令，三个步骤一次性完成。

 {% qnimg playgrounds/functions/introduction/2s.png title:tieMyShoe() alt:tieMyShoe() %}

<!-- ![tieMyShoe()](/images/functions/introduction/2s.png) -->


Coooool!

