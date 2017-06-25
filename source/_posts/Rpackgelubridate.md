---
title: R工具包-lubridate
date: 2017-06-22 13:51:02
tags: [R, lubridate]
---

## 前言
R语言用到了对于时间的处理

## 安装
```
install.packages("lubridate")
library("lubridate")
```

## API
ymd(), ymd_hms, dmy(), dmy_hms, mdy()
这一类是用来简化string转date，
这里再简单介绍下as_date，y代表2为年(16)，Y代表4位年(16)，m代表月份(12)，d表示日期(3)，b表示月份英文简写，B表示月份英文全称

year(), month(), mday(), hour(), minute() and second()
通过以上api获取日期的年月日时分秒

with_tz(), force_tz()
显示和改变时区

## 参考链接
[lubridate](https://github.com/tidyverse/lubridate)
[Dates and Times in R](https://www.stat.berkeley.edu/~s133/dates.html)

