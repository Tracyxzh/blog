---
title: 数据仓库
date: 2017-06-04 21:52:54
tags: [数据挖掘, 数据仓库, 数据库]
---

## 前言
最近在银联实习也算是做数据挖掘方面的工作，先前虽然有接触算法这一块，学校也开了机器学习这门课，但是对于数据仓库不是很了解。那个和厂商聊起来，他问我学过数据仓库吗，我没答应上来，所以今天准备好好学习下数据仓库。

## 定义
20世纪80年代中期，“数据仓库”（Data Warahouse， DW）这个名词首次出现在号称“数据仓库之父”W.H.Inmon（恩门）的Building Data Warahouse一书中。恩门把数据仓库定义为“一个面向主题的，集成的，稳定的，随时间变化的数据的集合，以用于支持管理决策过程”。

### 主题
面向主题组织的数据具有以下特点：
* 各个主题有完整，一致的内容以便在此基础上做分析处理
* 主题之间有重叠的内容，反映主题间的联系。重叠是逻辑上的，不是物理上的。
* 各主题的综合方式存在不同。
* 主题域应该具有独立性（数据是否属于该主题有明确的界限）和完备性（对该主题进行分析所涉及的内容均要在主题域内）。


### 集成性
数据仓库中存储的数据一般从企业原有已建立的数据库系统中提取出来，但并不是所有数据的简单拷贝，而是经过抽取、筛选、清理、转换、综合等工作得到的数据。

### 稳定性
数据仓库在某个时间段内来看是保持不变的。

### 随时间而变化
数据仓库大多关注的是历史数据，其中数据是批量载入的，即定期操作型应用系统中接收新的数据内容，这使得数据仓库中的数据总是拥有时间维度。

## 数据仓库系统

### 数据仓库组成
数据仓库系统通常指一个数据库环境，而不是指一件产品。数据仓库系统的一般体系结构如下图所示，整个数据仓库系统分为源数据层、数据存储和管理层、OLAP服务器层和前端分析工具层
![数据仓库组成](dataWarahouse/dw.jpeg)

<!-- more -->

## 参考书籍和链接
《数据仓库与数据挖掘概述》

## 每文音乐推荐
评论：
贾听听听不来课：Bob Dylan在给他在纽约的第一任女友Suze Rotolo的信中这样写道：这儿什么也没发生.狗在等着出门,贼在等着老妇人,孩子们在等着上学,条子们在等着揍人.每个人都在等着更凉快的天气.而我只是在等你.那些美好就在我们身边,但却没有被留意....

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=5057793&auto=1&height=66"></iframe>