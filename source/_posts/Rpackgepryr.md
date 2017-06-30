---
title: R工具包-pryr
date: 2017-06-23 09:52:49
tags: [R, pryr]
---

## 前言
今天学习R学习到了面向对象编程，以为自己对于面向对象应该是很了解了，但是发现里面有对歌面向对象系统，S3，S4，参考类，基础类型。不多说其他的，开始学习下pryr的使用，然后掌握这4个面向对象系统。

## 介绍
pryr是一个深入了解R底层的一个包

## API
* 方便理解内部实现的API:
	* promises对象：
	* 环境和作用域：
	* 闭包：
	* 函数调用关系：
	* 基础类型：
	* 复制和修改：
* 观察和理解R面向对象系统的API:
	* 判断对象属于哪个面向对象系统：otype()
	* 判断方法属于哪个面向对象系统：ftype()
* 辅助编程的API*
	* 改变创建函数：make_function(), f()
	* 表达式替换：substitute_q(), subs()
	* 修改：modify_lang()
	* 匿名函数：partial()
	* 函数匹配：find_funs()
* 代码简化工具：
	* 创建延迟或直接绑定：%<d-%, %<a-%
	* 创建常量：%<c-%
	* 重新绑定：rebind, <<-

## 安装
```
install.packages("pryr")
library(pryr)
```

## 参考链接
[github](https://github.com/hadley/pryr)
[博客](http://blog.fens.me/r-pryr/)