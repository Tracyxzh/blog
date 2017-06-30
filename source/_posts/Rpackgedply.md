---
title: R工具包-dplyr
date: 2017-06-21 23:12:32
tags: [R, dplyr]
---

# 前言
项目中用到了几个R语言的包，顺道仔细学习下


## 函数
name	Description
select()	选择列 # select(data, [-,start_with(), ends_with(),contains(),matches(),one_of()]olumn name, ...) 
filter()	行过滤 # filter(data, column name[>, <, >=, <=, !=, %in%] condition)
arrange()	整理行 # arrange(order, sleep_total) 排序
mutate()	新建列 # mutate(rem_proportion = sleep_rem / sleep_total) 
summarise()	统计  # summarise(avg_sleep = mean(sleep_total))
group_by()	分组 # group_by(order)

<!--more-->

## 管道函数 %>%
功能类似于Linux的管道|一样

# 参考链接
[plyr_tutorial](http://genomicsclass.github.io/book/pages/dplyr_tutorial.html)
