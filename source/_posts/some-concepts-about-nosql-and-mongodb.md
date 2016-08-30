---
title: MongoDB(3)–有关NoSQL及MongoDB的一些概念
date: 2011-09-29
categories: [NoSQL]
tags: [MongoDB, NoSQL]
---

学习任何东西在没有理解的前提下去背熟一些概念是没有用的，就像只背会了几个概念而没有理解的开发人员去面试是经不住面试官的追问的。前面的两篇对MongoDB做了简单的介绍，能够很快上手，对MongoDB有一个感性的认识。本篇大部分内容来自MongoDB权威指南和MongoDB实战。希望在学习完整个MongoDB后能对本篇的内容有一个全新的认识。

## NoSQL简介

NoSQL，全称是”Not Only Sql”,指的是非关系型的数据库。这类数据库主要有这些特点：非关系型的、分布式的、开源的、水平可扩展的。原始的目的是为了大规模 web  应用，这场全新的数据库革命运动早期就有人提出，发展至2009 年趋势越发高涨。NoSQL 的拥护者们提 倡运用非关系型的数据存储，通常的应用如：模式自由、支持简易复制、简单的API、最终

的一致性 （非ACID ）、大容量数据等。NoSQL 被我们用得最多的当数 key-value 存储，当然还 有其他的文档型的、列存储、图型数据库、xml 数据库等。相对于目前铺天盖地的关系型数 据库运用，这一概念无疑是一种全新思维的注入。

## NoSQL的优势

同关系型数据库相比，NoSQL有下面的一些优势：

* 适合对数据库高并发读写的需求。
* 适合对海量数据的高效率存储和访问的需求。
* 适合对数据库的高可扩展性和高可用性的需求。

由于NoSQL的这些优势，使得NoSQL比较适合以下的一些场景的使用：

* 对数据库事务一致性要求不高的时候，因为NoSQL不支持事务（MongoDB是不支持事务的，其他的没做研究）。
* 对数据库的写实时性和读实时性要求不高的时候。
* 对复杂的SQL 查询，特别是多表关联查询不多的时候。

## NoSQL的特点

* 它可以处理超大量的数据
* 它运行在便宜的它运行在便宜的 PC 服务器集群上服务器集群上，意思是在数据库不够用的时候进行PC的集群扩展很方便并且成本很低。
* 它击碎了性能瓶颈，因为使用NoSQL省去了传统的程序模型到SQL之间转换的时间，执行效率更高。
* 它没有过多的操作，意思是去掉了很多在关系数据库中拥有而在实际又不怎么使用的功能。
* 它的支持支持者源于社区者源于社区，所有的NoSQL产品都是开源的。

## MongoDB简介

MongoDB 是一个介于关系数据库和非关系数据库之间的产品，是非关系数据库当中功能最丰富，最像关系数据库的。他支持的数据结构非常松散，是类似json  的bjson 格式，简称BSON，因此可 以存储比较复杂的数据类型。MongoDB  最大的特点是他支持的查询语言非常强大，其语法有点类似于面向对象的查询语言，几乎可以实现类似关系数据库单表查询的绝大部分功能， 而且还支持对数据建立索引。它是一个面向集合的,模式自由的文档型数据库。

## MongoDB特点

### 1 丰富的数据模型

MongoDB是一种面向文档的数据库。在MongoDB中文档就相当于关系型数据库中的行。文档中可以包含很复杂的数据结构，这样一条记录就可以表示很复杂的层级关系。比如说文章表有一个字段是评论，在关系型数据库中我们通常会建一个评论表和文章表做关联，在MongoDB中就可以直接将评论存在一条文章记录的文档中。更符合我们的思维。

MongoDB没有模式，也就是说没有表结构，文档的字段可以随时添加，不会对原来数据有任何影响，使开发变得很容易。

### 2 容易扩展

在一些大型的网站中，数据的增长是非常惊人的。在面临数据增长机器不够用的时候通常有两种做法：

* 购买更高配置的机器，会花费很大，而且达到物理极限后花钱也买不到更高配置的了。
* 进行扩展，将数据分散到多个机器上，这种在操作上会显得复杂点。

MongoDB的设计就考虑到了扩展的问题，它所采用的面向文档的数据模型使得可以自动在多台服务器中切割数据。还可以平衡群集的数据和负载，自动进行文档重排。

### 3 丰富的功能

* 索引：MongoDB支持通用辅助索引，可以进行多种快速查询。
* 存储Javascript：不必再使用存储过程了，可以直接在服务器端存取Javascript的函数和值。
* 聚合：MongoDB支持MapReduce和其他聚合工具。
* 固定集合：集合的大小是有上限的，这对于日志一类的数据很有用。
* 存储文件：MongoDB支持用一种容易使用的协议（GridFS）来存储大型文件。

### 4 更快的速度

高性能是MongoDB的目标，为了提高性能，就必须进行很多精简的设计，相比关系型数据库少了很多功能，但仍然保持着关系型数据库的众多的特性。一些精简设计表现在：

* 使用MongoDB传输协议作为与服务器交互的主要方式，将比较HTTP、Reset等可以节省不少开销。
* 对文档进行动态填充，预分配数据文件，用空间换取时间，而且空间对于现在来说已不是问题。
* 默认的存储引擎使用内存映射文件，将内存管理工作交给OS去处理。
* 动态查询优化器会记住执行查询最高效的方式。

### 5 简单的管理

MongoDB尽量让服务器自治来简化数据库的管理。除了启动数据库服务器之外，几乎没有什么管理操作了。如果主服务器挂掉了，MongoDB会自动切换到备份服务器上，并将备份服务器提升为活跃服务器。在分布式的环境下，群集只需要知道有新的节点就会自动集成和配置新的节点。

## MongoDB适用场景

* 网站数据：MongoDB非常适合实时的插入，更新与查询，并具备网站实时数据存储所 需的复制及高度伸缩性 。
* 缓存：由于性能很高，MongoDB 也适合作为信息基础设施的缓存层。在系统重启之后， 由MongoDB 搭建的持久化缓存层可以避免下层的数据源过载 。
* 大尺寸，低价值的数据：使用传统的关系型数据库存储一些数据时可能会比较昂贵，在此之前，很多时候程序员往往会选择传统的文件进行存储 。
* 高伸缩性的场景：MongoDB  非常适合由数十或数百台服务器组成的数据库。MongoDB的路线图中已经包含对MapReduce 引擎的内置支持 。
* 用于对象及JSON 数据的存储：MongoDB 的BSON 数据格式非常适合文档化格式的存储及查询 。
