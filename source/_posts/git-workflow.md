---
title: Git工作流程
date: 2015-02-15
categories: [Git]
tags: [Git]
---

2014年初开始在公司推行Git的使用，到现在将近一年的时间，公司的大部分项目代码都已经迁移到了Git上，关于Git的安装使用在之前的文章有相关介绍，《[Windows 下使用Git管理Github项目](http://blog.fwhyy.com/2012/02/use-git-manage-github-project-on-windows/)》、《[在VS2010中使用Git【图文】](http://blog.fwhyy.com/2012/11/using-git-in-vs2010/)》，本文主要说说Git使用的工作流程。

一千个人心中有一千个哈莫雷特，Git作为一个源码管理工具在不同的人，不同的团队中使用的流程也是不相同的。下面说说我在公司推行的过程中在不同阶段的使用情况：

## 开始使用阶段

1、开始使用Git时，团队成员对Git还不是很了解，有的开发人员之前有VSS、SVN背景，有的没有使用过源码管理工具，使用过的也没有使用过分支功能；

2、开发人员每个人创建一个分支，随时随地commit，每天push一次到服务器；

3、因为每个人单独分支，push时不需要pull，也没有冲突需要解决；

4、团队Leader每天在所有开发人员push后将代码合并到master分支，开发人员每天上班后将master拉下来合并到自己分支；

## 产品/项目开始阶段

1、这时开发人员已基本熟悉Git的使用了，无需再每个人创建一个分支；

2、除了master分支还有一个供所有开发人员开发的dev分支；

3、大家都在同一个dev分支上进行工作，依然是随时随地地commit，每天push一次到服务器；

4、push代码前需要进行pull操作，因为有可能在之前有别的成员先进行了push操作，如果有冲突还需要进行冲突解决；

5、每天上班后所有成员对dev进行pull操作，获取所有成员push的代码，有冲突需要解决；

6、团队Leader每天将dev合并一次到master。

## 测试进入的阶段

1、测试可能是在项目后期才进入，不同公司或不同项目可能有所不同；

2、测试进入后就需要添加test分支；

3、在开发人员将代码push到dev分支后，可以在dev基础上创建test分支，测试人员以test分支搭建测试环境，开始测试；

4、开发人员在接受到bug后，直接在测试分支上修改，然后让测试人员进行验证；

5、每天团队Leader将测试分支上修改的bug合并到dev分支上，这样所有团队成员当天修复的bug都会在第二天被团队其他人pull下来；

6、团队Leader每天将dev合并一次到master。

## 上线后阶段

1、系统上线后试运行阶段会存在两种改动：Bug和优化需求，Bug通常当天解决晚上部署，优化需求通常周末部署；

2、Bug当天能修复的就直接在test分支上修复，然后进行测试，验证通过后合并到master；

3、Bug当天不能修复的就针对该Bug创建一个分支，修复完后合并到test分支进行测试，验证通过后合并到master；

4、每个优化需求都以master分支为基础创建一个feature分支，完成后合并到dev分支，开发人员可以先交叉测试，然后将dev合并到test进行测试，验证通过后合并到master；

5、master始终是一个干净的，可发布的分支。

## Commit提交的粒度

1、尽可能的越细越好；

2、每一次的提交应是相对独立的、完整的、有意义的；

3、注释越详细越好；

4、第一行概括本次提交的内容，言简意赅；

5、如果粒度够细，通常一句话可以概括，一句话不能概括的，空一行在下面写详细的注释；

6、太简单的注释还不如不写，没有任何意义；

7、据说林纳斯修改了20行的Liunx内核代码，注释长达2000多字，说明commit注释的重要性。

以上是我在实际工作中的一些心得，仅供参考，工具的使用没有最好，适合自己团队的才是最好的。第一次使用[刘韧体](http://mp.weixin.qq.com/s?__biz=MjM5NTI5MzM2MA==&mid=202105768&idx=1&sn=2ba05ca9c2711f3a1ed913073db2be2b&scene=2&from=timeline&isappinstalled=0#rd)，感觉还不错，[轻单网](https://qdan.me/)也是一种类刘韧体的延生，有兴趣的朋友可以去体验下。

