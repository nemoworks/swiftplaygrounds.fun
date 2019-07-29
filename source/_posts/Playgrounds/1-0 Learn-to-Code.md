---
title: 第一部分 开始学习写代码
categories:
  - Playgrounds
date: 2016-07-22 23:17:56
---



你是否曾经看着菜谱做过菜？或者按照说明书将玩具组装起来？做这些事情的时候，你按照菜谱或说明书上所给出的指令按顺序来做事，这与用指令让计算机运作是一个道理。

写代码可以让你创建自己的指令或命令，并让计算机按你指令来做事。以下内容就是教你学会用哪些指令、按什么顺序来指挥计算机做出各种神奇的事情。

Apple在iPad上发布了一个叫Swift Playgrounds的app，这个app展示了一个虚拟的迷宫世界，我们可以通过写一些命令让一个叫`Byte`的动画人物在这个世界中行走执行各种任务，从而学习Swift语言进行编程。

{% qnimg playgrounds/commands/introduction/1s.png title:Swiftplaygrounds alt:Swiftplaygrounds %}


在这个虚拟世界中，地面是有一个个正方形区域组成的，就像我们在地上铺的一块块地砖。我们的主角`Byte`执行一条"前进"指令

```
moveForward()
```

就可以到达前面一块地砖。当它站在宝石所在的那块地砖上时，你可以让它执行

```
collectGem()
```

指令来收集这颗宝石。

{% qnimg playgrounds/commands/introduction/2s.png title:虚拟世界 alt:虚拟世界 %}

<!-- ![虚拟世界](/images/commands/introduction/2s.png) -->

这些编程语言写的命令与我们人自己说的语言（自然语言）非常相似，只是将自然语言中的空格去掉而已。

> 当前Swift Playgrounds 应用只支持iOS 10的Beta版本，请用你的iPad访问[Apple Beta版软件计划网站](https://beta.apple.com)以安装最新版iOS 10。
