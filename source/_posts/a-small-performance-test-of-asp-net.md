title:  Asp.Net中的一个小的性能测试
date:  2007-01-03
url:  /2007/01/a-small-performance-test-of-asp-net/
categories: [Asp.Net]
tags:  [AspNet,性能]
---

大家都知道使用缓存可用大大提高asp.net应用程序的性能,那么究竟能提高多少性能呢?我做了一个小小的测试.

1 在vs2003中新建一个web应用程序,在页面上添加一个DataGrid控件，让DataGrid里显示NorthWind数据库中employees表的内容。我的做法是在vs2003的服务器资源管理器中建立一个连接到NorthWind数据库的连接，然后将其中的employees
<!--more-->
表拖到页面中，如图：

[![](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214625.gif "2010-12-30_214625")](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214625.gif)

[](http://blog.photo.sina.com.cn/showpic.html#blogid=3cefded1010006yy&amp;url=http://static12.photo.sina.com.cn/orignal/3cefded12e00baf7d012b)[](http://blog.photo.sina.com.cn/showpic.html#blogid=3cefded1010006yy&amp;url=http://static15.photo.sina.com.cn/orignal/3cefded17529a5fa1a54e)

【当然还有别的方法连接数据库】。

这样就自动生成了sqlDataConnection1和sqlDataAdapter1，右击sqlDataAdapter1点击生成数据集，根据向导生成数据集dataSet11。

2 双击页面进入.cs文件下（我用的是C＃语言），首先导入命名空间，然后在Page_Load中写如下代码：

[![](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214704.gif "2010-12-30_214704")](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214704.gif)

[](http://blog.photo.sina.com.cn/showpic.html#blogid=3cefded1010006yy&amp;url=http://static2.photo.sina.com.cn/orignal/3cefded13a4031a125051)[](http://blog.photo.sina.com.cn/showpic.html#blogid=3cefded1010006yy&amp;url=http://static11.photo.sina.com.cn/orignal/3cefded165e5f2ac4eaaa)

按F5运行，就能看见DataGrid控件中显employees表中的数据。

3 显示做完了，现在就开始测试了，打开vs2003自带的测试工具－MicroSoft Application Center Test如图：

[![](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214748.gif "2010-12-30_214748")](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214748.gif)

[](http://blog.photo.sina.com.cn/showpic.html#blogid=3cefded1010006yy&amp;url=http://static14.photo.sina.com.cn/orignal/3cefded14365dfacbc1dd)

[](http://blog.photo.sina.com.cn/showpic.html#blogid=3cefded1010006yy&amp;url=http://static14.photo.sina.com.cn/orignal/3cefded1aef187d9c39cd)

打开了测试工具后，点击文件下面的新建项目来新建一个测试项目，在新建的测试项目上右击新建一个测试，根据向导完成。在页面没用缓存和使用了缓存分别做一次。就能看见出明显的差别了。使用页面缓存方法是：将页面切换到HTML代码模式，在上面加上OutpurCache指令。

如:[%@OutputCache Duration="60" VaryByParam="none" %](mailto:%25@OutputCache%20Duration=)

下面两张图为使用缓存前后的结果对比图

**使用前：**

[![](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214826.gif "2010-12-30_214826")](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214826.gif)

[](http://blog.photo.sina.com.cn/showpic.html#blogid=3cefded1010006yy&amp;url=http://static10.photo.sina.com.cn/orignal/3cefded1bca67bf28c9a9)

**使用后：**

[![](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214859.gif "2010-12-30_214859")](http://blog.fwhyy.com/wp-content/uploads/2010/12/2010-12-30_214859.gif)

[](http://blog.photo.sina.com.cn/showpic.html#blogid=3cefded1010006yy&amp;url=http://static2.photo.sina.com.cn/orignal/3cefded149d7b13b1d7a1)

很明显可以看出使用页面缓存和性能提高了4倍多


