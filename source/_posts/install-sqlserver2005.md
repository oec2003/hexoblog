---
title: SharePoint2007安装图文详解三：安装SqlServer2005
date: 2011-01-11
categories: [MOSS]
tags: [SharePoint, SqlServer]
---

SharePoint2007 中的很多功能会用到数据库，如分析服务，报表服务等。本文介绍SqlServer2005的安装，数据库的安装很简单，基本上安装默认选项点击下一步即可，需要注意的地方在下面会提到。

现在就开始安装SqlServer2005 ，运行Setup.exe

![2011-01-10_100800](http://oec2003.qiniudn.com/2011-01-10_100800.gif)

选中“我接受许可条款和条件”，点击“下一步”

![2011-01-10_113025](http://oec2003.qiniudn.com/2011-01-10_113025.gif)

点击“安装”

![2011-01-10_113725](http://oec2003.qiniudn.com/2011-01-10_113725.gif)

点击“下一步”

![2011-01-10_113911](http://oec2003.qiniudn.com/2011-01-10_113911.gif)

点击“下一步”

![2011-01-10_113957](http://oec2003.qiniudn.com/2011-01-10_113957.gif)

点击“下一步”

![2011-01-10_114354](http://oec2003.qiniudn.com/2011-01-10_114354.gif)

点击“下一步”

![2011-01-10_114427](http://oec2003.qiniudn.com/2011-01-10_114427.gif)

点击“高级”

![2011-01-10_120035](http://oec2003.qiniudn.com/2011-01-10_120035.gif)

根据需要选择需要安装的服务，此处我将所有的都选择了，点击“下一步”

![2011-01-10_120318](http://oec2003.qiniudn.com/2011-01-10_120318.gif)

选择“默认实例”，点击“下一步”

![2011-01-10_144340](http://oec2003.qiniudn.com/2011-01-10_144340.gif)

选择“使用域用户账户”，输入用户名和密码，域填写在安装AD时配置的域名称。填写完后点击“下一步”

![201101111515433034](http://oec2003.qiniudn.com/201101111515433034.gif)

选择“Windows身份验证模式”，点击“下一步”

![2011-01-10_145622](http://oec2003.qiniudn.com/2011-01-10_145622.gif)

按照默认，点击“下一步”

![2011-01-10_145752](http://oec2003.qiniudn.com/2011-01-10_145752.gif)

选择“安装默认配置”，点击“下一步”

![2011-01-10_145938](http://oec2003.qiniudn.com/2011-01-10_145938.gif)

点击“下一步”

![2011-01-10_150028](http://oec2003.qiniudn.com/2011-01-10_150028.gif)

点击“安装”

![2011-01-10_150143](http://oec2003.qiniudn.com/2011-01-10_150143.gif)

现在等他自己安装就行了，我们可以去做做别的事情。

![2011-01-10_153124](http://oec2003.qiniudn.com/2011-01-10_153124.gif)

到现在SqlServer2005已经安装成功了。

## 相关文章

[SharePoint2007安装图文详解一：安装IIS及相关组件](http://blog.fwhyy.com/2011/01/iis-install/)
[SharePoint2007安装图文详解二：安装AD（活动目录）及DNS](http://blog.fwhyy.com/2011/01/installation-of-ad-and-dns/)
SharePoint2007安装图文详解三：安装SqlServer2005
[SharePoint2007安装图文详解四：安装.NET Framework 3.0和SharePoint 2007](http://blog.fwhyy.com/2011/01/installation-of-the-net-framework-3-0-and-sharepoint-2007/)


