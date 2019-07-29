---
title: 1.5 寻找并修复代码中的“臭虫” (Finding and Fixing Bugs)
categories:
  - Playgrounds
date: 2016-07-24 14:01:27
---


我们写的代码难免会出错，执行代码中的命令产生的结果不是你想要的。这写错误叫做“臭虫”（Bug）。比如本关刚开始给出的代码就是错的，你可以直接执行试试看。

{% qnimg playgrounds/commands/findingandfixingbugs/1s.png title:错误的代码 alt:错误的代码 %}

<!-- ![错误的代码](/images/commands/findingandfixingbugs/1s.png) -->

仔细想想这个代码为什么是错的？因为`Byte`拐弯拐早了，不是么？

 {% qnimg playgrounds/commands/findingandfixingbugs/2s.png title:错误原因 alt:错误原因 %}

<!-- ![错误原因](/images/commands/findingandfixingbugs/2s.png) -->


发现错误并了解了错误产生的原因后，我们可以想法子修复这个错误。很简单，让`Byte`晚点拐弯就行了。你可以用手指在屏幕上点中`turnLeft()`这个命令然后拖动，也可以选中命令然后拷贝并黏贴到合适的位置。

 {% qnimg playgrounds/commands/findingandfixingbugs/3s.png title:解决错误 alt:解决错误 %}

<!-- ![解决错误](/images/commands/findingandfixingbugs/3s.png) -->


然后，重新运行代码看看是不是正确了。如果还不对，那重复以上过程：观察发现错误->思考错误原因->调整代码解决错误。

 {% qnimg playgrounds/commands/findingandfixingbugs/4s.png title:解决错误 alt:解决错误 %}

<!-- ![解决错误](/images/commands/findingandfixingbugs/4s.png) -->

能完成这一步，你可以认为自己已经是码农了。
