---
title: R工具包-RMySQL和数据处理和加工相关包
date: 2017-06-26 11:12:41
tags: [R, Mysql]
---

## 前言
R要处理的数据保存在数据库中，应考虑R与MySQL之间的数据输入和输出问题，RMySQL包正是为了解决这些问题而推出的。

## RMySQL
### 安装
```
install.packages("RMySQL")
library(RMySQL)
```

### MySQL函数
```
RMySQL::dbConnect : 连接数据库
RMySQL::dbConnect(
	drv,
	user,
	password,
	dbname,
	host
)
返回连接对象
```

<!--more-->

```
RMySQL::dbListTables : 获取数据库中的数据表列表
RMySQL::dbListTables(
	conn # 数据库连接
)
返回数据库中的列表
```

```
RMySQL::dbGetQuery : 想数据库运行给定查询
RMySQL::dbGetQuery(
	conn,
	statment
)
```
## 数据处理和加工相关包
```
包           |  用途
sqldf        |  使用SQL处理数据
plyr         |  拆分数据，对拆分的数据应用apply函数，合并结果
reshape2     |  数据整理与汇总
data.table   |  代替R数据框更快的数据类型
foreach      |  用途
doParaller   |  用途 
testthat     |  用途
```

## 参考资料
[github](https://github.com/rstats-db/RMySQL)