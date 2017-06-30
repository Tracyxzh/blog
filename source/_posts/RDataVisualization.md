---
title: R数据可视化-ggplot2
date: 2017-06-22 09:46:03
tags: [R, 数据可视化]
---

## 前言
数据可视化是最直观的展示数据的一种方式。R语言提供了多种绘图系统，借助它们可以轻松绘制散点图(scatter plot)、折线图(graph of broken line)、条形图(bar graph)、箱线图(box plot)等。R的绘图功能主要由graphics、lattice、ggplot这3个包提供

## plot
```
plot(
	x,     # x
	y,     # y
	xlab,  # 横坐标name
	ylab,  # 纵坐标name
	main,  # 图name
	pch,   # 点类型
	cex,   # 点大小
	col,   # 点颜色
	xlim,  # x范围
	ylim,  # y范围
	type   # 图像类型，p点，l线，b点线
)
```

## par
```
使用plot绘图，每次都会新建一个窗口，可以使用par
par(
	... # 采用tag = value 方式设置参数
)
```

## jitter
```
jitter(
	x,              # 数据
	factor = 1,     # 设置噪声水平
	amount = null
)
```

points、lines、abline在plot的图纸上添加点和线、直线


## 安装
install.packages("tidyverse")
library(tidyverse)

## 绘图函数
ggplot(data = <DATA>) + 
  <GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))


## 例子
```
ggplot(data = mpg) + 
  geom_point(mapping = aes(x = displ, y = hwy, size = class))
说明:
mpg是这个包中自带的一份数据，这个数据是美国环境保护局对于38种车型的统计数据


mpg
#> # A tibble: 234 × 11
#>   manufacturer model displ  year   cyl      trans   drv   cty   hwy    fl
#>          <chr> <chr> <dbl> <int> <int>      <chr> <chr> <int> <int> <chr>
#> 1         audi    a4   1.8  1999     4   auto(l5)     f    18    29     p
#> 2         audi    a4   1.8  1999     4 manual(m5)     f    21    29     p
#> 3         audi    a4   2.0  2008     4 manual(m6)     f    20    31     p
#> 4         audi    a4   2.0  2008     4   auto(av)     f    21    30     p
#> 5         audi    a4   2.8  1999     6   auto(l5)     f    16    26     p
#> 6         audi    a4   2.8  1999     6 manual(m5)     f    18    26     p
#> # ... with 228 more rows, and 1 more variables: class <chr>

aes(x = displ, y = hwy)：
这里是绘制displ和hwy关系的二维图像
size = class:
对于图像中的点根据class分类使用不同的大小，这里还可以使用color，shape，alpha，这几个单词的字面意思，大家可以动手实现一下

```
## 切分图像
```
ggplot(data = mpg) + 
  geom_point(mapping = aes(x = displ, y = hwy)) + 
  facet_wrap(~ class)
facet_wrap 第一个参数是切分依据的字段，该字段需要是离散的
```
<!--more-->

## 线性
```
ggplot(data = mpg) + 
  geom_smooth(mapping = aes(x = displ, y = hwy))
说明：
geom_smoothgenjudispl和hwy线性拟合，如果加上入入geom_point后一样的分类现实例如：color=drv,将根据drv分类拟合并且显示不同的颜色

```

## 统计
```
diamonds
# A tibble: 53,940 x 10
   carat       cut color clarity depth table price     x     y     z
   <dbl>     <ord> <ord>   <ord> <dbl> <dbl> <int> <dbl> <dbl> <dbl>
 1  0.23     Ideal     E     SI2  61.5    55   326  3.95  3.98  2.43
 2  0.21   Premium     E     SI1  59.8    61   326  3.89  3.84  2.31
 3  0.23      Good     E     VS1  56.9    65   327  4.05  4.07  2.31
 4  0.29   Premium     I     VS2  62.4    58   334  4.20  4.23  2.63
 5  0.31      Good     J     SI2  63.3    58   335  4.34  4.35  2.75
 6  0.24 Very Good     J    VVS2  62.8    57   336  3.94  3.96  2.48
 7  0.24 Very Good     I    VVS1  62.3    57   336  3.95  3.98  2.47
 8  0.26 Very Good     H     SI1  61.9    55   337  4.07  4.11  2.53
 9  0.22      Fair     E     VS2  65.1    61   337  3.87  3.78  2.49
10  0.23 Very Good     H     VS1  59.4    61   338  4.00  4.05  2.39
# ... with 53,930 more rows

ggplot(data = diamonds) + 
  geom_bar(mapping = aes(x = cut))
说明：
直方图，横坐标是cut，纵坐标默认是count，可以改变图像的颜色，fill属性改变填充色，color属性改变外围色，alpha改变透明度
```


## 参考链接
[Data visualisation](http://r4ds.had.co.nz/data-visualisation.html)
[PDF](http://vita.had.co.nz/papers/layered-grammar.pdf)
