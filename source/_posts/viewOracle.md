---
title: 视图 -- 数据库中的虚拟表
date: 2017-06-03 10:19:35
tags: [oracle, 数据库]
---

## 前言
最近在银联实习，实习的内容是基于大数据平台的项目。目前的主要工作内容是数据准备，这需要接触到存储过程以及spark sql，存储过程中还有一些视图。对于存储过程了解程度由于前段时间学习过了，所以基本可以了，所以今天准备学习下视图这方面的知识。

## 定义
视图：是一个基于一个或者多个表的逻辑表，视图本身不包括任何数据。

## 数据源
* 单一表的子集
* 多表操作的结果集
* 视图的子集

## 语法
```
CREATE [ OR REPLACE ] [ [ ON ] FORCE ] VIEW
[ schema. ] view
[ (alias, ...) inline_constraint(s) ]
[ out_of_line_constrain(s) ]
AS subquery
[
	WITH { READ ONLY | CHECK OPTION [ CONSTRAINT constraint ] }
]
[说明]
OR REPLACE:创建视图的时候如果存在同名视图则覆盖
[ ON ] FORCE :表示是否强制创建，如果基表不存在的情况下创建视图会出现错误，强制创建可以先创建视图然后再创建基表。
[ schema. ] view:视图所属方案或者视图的名称
[ (alias, ...) inline_constraint(s) ]:视图字段的别名和内联约束
[ out_of_line_constrain(s) ]:也是约束
WITH READ ONLY:视图只读
WITH CHECK OPTION [ CONSTRAINT constraint ]:一旦使用该约束，当视图增加或修改数据时必须满足子查询的条件。
```
<!-- more -->

## 参考书籍和链接
《oracle 入门》

## 每文音乐推荐
评论：
* 卖大白菜的：我有一老友，已经死掉了。她有双相情感障碍，对药物精神依赖，长期使用LSD，不健康，不自由，认为整个世界都在拒绝她，喜摇滚，爱抽烟，很酷，出众，也很脆弱，与3、4个14、5岁的少年相互戏弄被侮辱，溺亡在夏日黎明里的一块水塘。她的社交签名留着那句：他人即地狱。她肯定喜欢这首歌。
* BeckyT-T：有些歌听着会觉得孤独真好，人生终究是自己的人生，任何人无法代替。

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=17810607&auto=1&height=66"></iframe>