---
title: 1.6 继续“捏臭虫” (Bug Squash Practice)
categories:
  - Playgrounds
date: 2016-07-24 14:01:40
---


这一关我们继续练习如何修复程序错误。同样，先直接运行当前的代码，你发现`Byte`把一个原本开着的开关给关了，然后走到了迷宫边缘，任务当然没有完成。

> 本关的任务是把所有的开关打开，并拿到宝石。

 {% qnimg playgrounds/commands/bugsquashpractice/1s.png title:错误的代码 alt:错误的代码 %}

<!-- ![错误的代码](/images/commands/bugsquashpractice/1s.png) -->

跟上一关一样，观察一下代码的执行，你会发现实际上`Byte`应该早点转弯，所以我们得把`turnLeft()`这个命令提前。

> 注意，本关和前一关为了让你练习找错误，不允许你直接输入命令而只能调整原有代码中的命令顺序。如果可以输入新的命令的话我们当然可以在原有代码中插入很多命令让`Byte`多走点路完成任务。

 {% qnimg playgrounds/commands/bugsquashpractice/2s.png title:调整命令 alt:调整命令 %}

<!-- ![调整命令](/images/commands/bugsquashpractice/2s.png) -->


好，把`turnLeft()`上移后重新运行，你发现`Byte`最后还是没有拿到宝石，因为它在没有宝石的那块地砖上提前做了个拿宝石的动作，而最后到了宝石那儿却什么都没做。

 {% qnimg playgrounds/commands/bugsquashpractice/3s.png title:调整命令 alt:调整命令 %}

<!-- ![调整命令](/images/commands/bugsquashpractice/3s.png) -->

如何修复后面这部分？很简单了，你自己来。

 {% qnimg playgrounds/commands/bugsquashpractice/4s.png title:完成任务 alt:完成任务 %}

<!-- ![完成任务](/images/commands/bugsquashpractice/4s.png) -->

大功告成了，码农朋友。