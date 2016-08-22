---
title: 使用Expression Encoder 3发布媒体文件到WebDAV
date: 2010-04-20
categories: [WMS]
tags: [Expression Encoder3, WMS]
---

## 使用环境

Windows Server 2008

IIS7.0  Microsoft

Expression Encoder3

## 准备

在IIS7.0中没有自带WebDAV，可以通过下面的链接进行下载安装，后两个为补丁。

[Microsoft WebDAV Extension for IIS 7.0 (x86)](http://www.microsoft.com/downloads/details.aspx?FamilyID=036269fa-0040-4ccd-ad3d-78da1ee132fb&DisplayLang=en)
[Microsoft WebDAV Extension for IIS 7.0 (x64)](http://www.microsoft.com/downloads/details.aspx?FamilyID=13e97aaa-fb1b-4cf8-b95f-19ae02321385&DisplayLang=en)
[Update for WebDAV Extension for IIS 7.0 (KB955137) (x86)](http://www.microsoft.com/downloads/details.aspx?FamilyID=567cb0d6-3e94-4035-a79d-22d1ef307d5e&DisplayLang=en)
[Update for WebDAV Extension for IIS 7.0 (KB955137) (x64)](http://www.microsoft.com/downloads/details.aspx?FamilyID=31fc62d7-abd0-4ac0-b727-d5ef0a50f8cc&DisplayLang=en[/url])
[Smooth Streaming（x86 x64）](http://www.iis.net/download/SmoothStreaming)

## 安装

根据个人的电脑系统选择下载的安装包进行安装，如下图：

![2010-04-20_161454](http://oec2003.qiniudn.com/2010-04-20_161454.png)

安装WebDAV

![2010-04-20_171133](http://oec2003.qiniudn.com/2010-04-20_171133.png)

安装Smooth Streaming

设置及使用

安装好WebDAV后，打开“Internet 信息服务（iis）管理器”，新建一个Web站点TestEncoder  ，指向D://TestEncoder目录。点击新建的站点在功能区会看到“WebDAV Authoring Rules ” 选项，如下图

![2010-04-20_162328](http://oec2003.qiniudn.com/2010-04-20_162328.png)

双击[WebDAV Authoring Rules ]项，右边的操作界面如下：

![2010-04-20_162540](http://oec2003.qiniudn.com/2010-04-20_162540.png)

首先点击Disable WebDAV 启用WebDAV，然后点击Add Authoring Rule… 添加规则，下图仅供参考，具体设置根据实际应用来

![2010-04-20_162726](http://oec2003.qiniudn.com/2010-04-20_162726.png)

再点击WebDAV Settings进行设置，如下：

![2010-04-20_162950](http://oec2003.qiniudn.com/2010-04-20_162950.png)

设置好了后点击“应用”就可以了。

到目前为止已经将WebDAV安装好了，不过还要对站点TestEncoder进行一些设置才可以：

a 点击站点TestEncoder，在中间功能板块中双击“身份验证”，然后启用“windows 身份验证”。

![2010-04-20_170732](http://oec2003.qiniudn.com/2010-04-20_170732.png)

b 点击站点TestEncoder，在中间功能板块中双击“目录浏览”，然后启用目录浏览。

现在就开始完成发布过程。

1  打开Expression Encoder3 ，新建一个JOb，名为为TestWebDAV，在媒体内容区域点击“导入”从本地选择一个媒体文件。

![2010-04-20_164233](http://oec2003.qiniudn.com/2010-04-20_164233.png)

2  在“编码”面板中选择输出格式为“IIS Smooth Streaming ” 。

![2010-04-20_165100](http://oec2003.qiniudn.com/2010-04-20_165100.png)

3  在“输出”面板中，任意选择一个模板，这个模板是Silvelight播放器的样式的模板，选择后再下方会有一个效果的预览视频。

![2010-04-20_165319](http://oec2003.qiniudn.com/2010-04-20_165319.png)

4  在“输出”面板中展开“发布”节点，设置如下图：

![2010-04-20_170127](http://oec2003.qiniudn.com/2010-04-20_170127.png)

5  在“媒体内容”面板中点击“编码”，首先是对媒体文件进行编码，编码完成后就会直接发布到先前创建的站点TestEncoder  中。通过地址[http://192.168.1.160:8080/TestWenDAV/default.html](http://192.168.1.160:8080/TestWenDAV/default.html) 可以直接访问了。


