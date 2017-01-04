---
title: 'C#给PDF添加编辑域'
date: 2017-01-04 22:13:36
categories: [C#]
tags: [C#,iTextSharp,PDF]
---

PDF文档通常是不能编辑的，但有些时候需要在PDF文档中填写日期或签名之类，就需要在PDF有能编辑的文本域，本文介绍怎样用C#来实现这一功能。

## 环境

工具：VS2015
语言：C#
操作PDF类库：iTextSharp 5.5.10
生成的PDF预览的工具：Skim、福昕阅读器、Acrobat Reader

## 代码实现

### 获取文档的页数

```
PdfReader reader = new PdfReader(@"C:\WorkSpace\1.pdf");
```

### 创建文本域

```
TextField fieldDate = new TextField(stamp.Writer, new iTextSharp.text.Rectangle(105, 100, 240, 125), "date");
```

`iTextSharp.text.Rectangle(105, 100, 240, 125)` 用来设置文本域的位置，四个参数分别为：llx、lly、urx、ury：

* llx 为Left ，lly 为Bottom,urx 为Right，ury 为Top

### 创建文本

```
Chunk cname = new Chunk("Date:", FontFactory.GetFont("Futura", 16f,new BaseColor(170,64,0)));
```

### 完整代码

```
public static void AddTextField()
```
