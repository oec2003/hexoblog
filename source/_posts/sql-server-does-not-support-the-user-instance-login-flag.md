---
title: 解决“此版本的 SQL Server 不支持用户实例登录标志。该连接将关闭”问题
date: 2011-02-22
categories: [SqlServer]
tags: [SqlServer, 错误解决]
---

错误提示

![20110222-001](http://oec2003.qiniudn.com/20110222-001.png)

出现此错误的原因为在webconfig连接字符串中的;User Instance设置为True了，将;User Instance值修改为false即可解决此问题。


