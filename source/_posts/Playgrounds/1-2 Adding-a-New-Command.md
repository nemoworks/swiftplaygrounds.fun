---
title: 1.2 使用一个新命令 (Adding a New Command)
categories:
  - Playgrounds
date: 2016-07-23 16:39:18
---


本关卡跟上一个很类似，但你发现这次想让`Byte`走到宝石那儿的话，你需要让他向左转一次。这个动作依靠给它发送新的`turnLeft()`命令来实现：

{% qnimg playgrounds/commands/addinganewcommand/1s.png title:左转命令 alt:左转命令 %}

<!-- ![左转命令](/images/commands/addinganewcommand/1s.png) -->

很简单，你自己试一下。然后再点“Next Page”继续下一关。


> 注意，`Byte`需要走的步数只跟它前进方向需要跨过的地砖数有关，上下台阶不需要额外算步数，如图所示。

{% qnimg playgrounds/commands/addinganewcommand/2s.png title:前进步数问题 alt:前进步数问题 %}

<!-- ![前进步数问题](/images/commands/addinganewcommand/2s.png) -->
