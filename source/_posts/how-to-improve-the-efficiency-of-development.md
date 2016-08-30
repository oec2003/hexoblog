---
title: 怎样提高开发效率
date: 2012-10-21
categories: [经验总结]
tags: [经验总结]
---

## 前言

给你一个任务,限定5天内完成,如果你实际用了6天,可以说是开发效率不高,或者同样的一个任务,你花了6天,而你的同事却只用了4天,也可以说是你的开发效率不高,影响开发效率的因素有很多,下面就我个人的理解来谈谈怎样提高开发效率.

## 工具

俗话说，工欲善其事必先利其器，使用得心应手的工具必然会提高开发效率，做微软平台开发的肯定离不开VS，就VS本身来说，除了常用功能外一些常用的快捷键一定要能熟练运用，例如下面是我认为比较有用的几个快捷键：

* 注释： Ctrl + K + C
* 取消注释： Ctrl + K + U
* 全屏： Shift + Alt + Ente
* 设置标签： CTRL + K, CTRL + K
* 下一个、上一个标签： CTRL + K, CTRL + P 、CTRL + K, CTRL + P
* 列出成员： Ctrl + J
* 显示参数信息： Ctrl + Shift + Space
* 转到定义后返回： Ctrl + –

熟练使用快捷键对于代码编写的速率和跟踪代码的速率会有大大的提高。

有时候开发工具自身的功能受到了限制，这是就需要使用插件来丰富功能，这里推荐两款插件，VS中的ReSharper和SqlServer中的SQL prompt5，ReSharper是功能很强大的一个VS插件，但会拖慢VS的速度，就看怎么去权衡了，我在之前的博文《[强大的VS插件—Resharper](http://blog.fwhyy.com/2009/10/powerful-vs-plug-in-resharper/)》做过简单介绍。SQL prompt5是SqlServer的一个插件，功能也非常强大，有很强的智能提示功能，所提供的SQL Search功能可以对数据库对象进行快速查找，还提供代码片段功能，在我之前的博文《[SqlServer开发利器—SQL Prompt5](http://blog.fwhyy.com/2012/10/using-sql-prompt5/)》中也做过介绍。

除了我们每天都离不开的VS和SqlServer之外还有一些辅助的开发工具也可以来帮助我们来提高效率，我经常使用的有以下几种：

* SqlDbx：很小巧的一款数据库管理工具，但功能非常强大，支持多种数据库，经常使用他的智能提示和生成脚本等功能，但也有缺点，对中文支持的不是很好；
* Aptana：该工具可以说是做Web开发的利器了，我有时写JS会用到该工具，有一个亮点之处是智能提示能够显示不同浏览器是否支持；
* Free Javascript Editor：可以很方便的写一些简单的HTML和JS代码并运行，可以直接选择JS的代码片段进行执行，对JS的调试也很方便。

还有一些其他的工具也非常有用，比如我在平时的工作中会经常用到Total Commander和Everything：

* Total Commander：资源管理器的代替工具，支持多标签，可以很方便的对文件进行操作；
* Everything：一款搜索工具，速度奇快，以前也做过介绍《软件推荐：磁盘搜索软件Everything》。

## 代码沉淀

有点规模的软件公司都会有自己的开发框架，这些框架都是多少年积累的产物，目的就是为了提高开发效率，作为一个开发人员平时对于一些常用的代码也应该有自己的沉淀，不光自己沉淀，在组内也应互相分享，记录这些沉淀的代码就可以根据自己的喜好了，记事本、Word、Excel、OneNote等都可以。沉淀的代码还可以使用VS的代码片段功能来进行管理，VS2010中对代码片段支持的很好，上面提到的SqlServer的插件SQL Prompt5也提供了数据库中的代码片段功能。

VS中给我们提供了很多现成的代码片段，要使用自定义的代码片段最方便的就是使用代码片段制作工具，工具点击[此处](http://snippeteditor.codeplex.com/)下载，当然也可以自己创建代码片段文件，然后在VS中导入即可，代码片段文件其实就是一个xml格式的文件，后缀为snippet。

代码质量

代码质量好了，产生的bug就少，和测试的交互也就少了，也就不会因为前面产生的bug而影响后面的进度，效率自然就高了。代码质量可以分三个方面来看：

1 代码出错少，能够正常的运行；

* 主动学习，提升自我的编程技能；
* 勤思考，对干过的错要经常总结，一些规范性的原则要牢记，这些常常会出现一些低级错误；
* 一个任务做完后需要进行充分的自测。

2 代码的运行效率高，在大数据、高并发的时候能够高效运行；

* 高性能的开发得从点滴做起，不放过每一个细节，可能一个小的细节点就是一个性能的瓶颈；
* 要有重构代码的习惯，好的代码是重构出来的，高性能的代码也是重构出来的；
* 多学习一些原理性的知识，不光要知其然还是知其所以然，基础扎实了，一些性能的问题就知道怎么去优化了；
* 之前翻译过几篇关于C#代码简化的博文，参见《[C#/Net代码精简优化技巧（1）](http://blog.fwhyy.com/2010/10/csharp-net-code-concise-optimization-techniques-1/)》、《[C#/Net代码精简优化技巧（2）](http://blog.fwhyy.com/2010/10/csharp-net-code-concise-optimization-techniques-2/)》、《[C#/Net代码精简优化技巧（3）](http://blog.fwhyy.com/2010/11/csharp-net-code-concise-optimization-techniques-c/)》

3 代码最后的运行结果要和客户的要求一致；

* 做需求之前把自己的理解跟需求分析进行沟通看是否能达成一致，如果是直接和客户进行沟通可以先做出小Demo，然后给客户演示，根据反馈不断改进；
* 在做的过程中如果遇到有疑问的地方一定要和需求或客户进行沟通，不要根据自己的想法想当然的去进行代码编写；
* 必要的时候可以引导客户，我们的主要目的能以最有效的方式帮客户解决问题，不能盲目的按照客户的要求来，有时客户说需要一双雨鞋，可能一把伞就可以解决问题。同样对于需求分析写的文档，开发也需要有质疑的精神。

## 业务知识学习

做任何的系统都避免不了有业务背景，熟练的了解业务知识可以使我们更清楚的知道我们是在做什么。很多的开发人员可能只喜欢钻研技术，对业务往往没什么兴趣，代码写完了，可能还不知道做出的模块时做什么用的，这样写出来的代码的质量就可想而知了。

* 学习业务可能很枯燥，但却是一劳永逸的事情，所以不管是否有兴趣，还是应该硬着头皮啃下来；
* 小组内可以成立兴趣小组，探讨的方式来进行学习，互相分享各自的学习内容，关键是组内的氛围要搞起来；
* 如果是直接跟客户沟通，需要用客户能听懂的语言，比如图文配合或是一些小Demo，否则当开发术语碰上领域术语就可能都是在对牛弹琴了。

总之，作为一名开发人员，要时刻想着怎样来提高开发效率，开发效率的提高是你在工作中一个良性循环的开始。如果您有好的方法和建议，欢迎一起分享。

