---
title: R常用函数和数据结构
date: 2017-06-21 11:14:05
tags: [R]
---

# 前言
开始了R语言的学习

## 基础函数
```
# 首先要学习的函数
? # 和help函数一样
str # struture的简写

# 重要的运算符和赋值函数
%in%, match  # a%in%y 判断a是否为y中的元素
=, <-, <<- # x=c(1,2,3) x<<-x*2 结果 x=c(2,4,6)更新x的值
$, [, [[, head, tail, subset # head(1:50, 10) [1]1  2  3  4  5  6  7  8  9 10 tail(1:50, 10)  [1] 41 42 43 44 45 46 47 48 49 50
with
assign, get

# 比较
all.equal, identical # identical(a,b) 判断对象是否相同 
!=, ==, >, >=, <, <=
is.na, complete.cases
is.finite

# 基础数学
*, +, -, /, ^, %%, %/% # %% 取余 # %/% 取整
abs, sign # sign 指示函数
acos, asin, atan, atan2
sin, cos, tan
ceiling, floor, round, trunc, signif # trunc 去除小数  signif(data, n) data 精确的位数为n，包括整数
exp, log, log10, log2, sqrt
max, min, prod, sum # prod 连乘
cummax, cummin, cumprod, cumsum, diff # cu开头的函数计算累计值 # diff计算间隔
pmax, pmin  # pmax(x,y,z) 返回x,y,z各列的最大值
range # 取出最大最小值
mean, median, cor, sd, var # cor 相关系数  sd 均方差Standard Deviation var 方差
rle # Run Length Encoding 连续变量统计

# 处理函数的函数
function
missing
on.exit
return, invisible

# 逻辑与集合
&, |, !, xor  # &, | 用于对保存逻辑值的向量进行运算运算，并按元素逐个进行
&&, || # &&, ||  &&并不用于在向量的元素之间的运算，它用于运算两个逻辑值
all, any
intersect, union, setdiff, setequal # union 求合集 intersect 求交集 setdiff 求差集 setequal 判断x和y是否相同
which # 用法which(test)。返回test为真值的位置 

# 向量与矩阵
c, matrix
# 强制转换规则字符型(character)>数值型(numeric)逻辑型(logical)
length, dim, ncol, nrow
cbind, rbind
names, colnames, rownames # names 定义或返回向量c的元素名字
t # 求转置
diag
sweep
as.matrix, data.matrix

# 构建向量
c
rep, rep_len # 保存重复向量值的向量 rep(x,times,each) x:保存重复的向量 times:整个向量重复的次数 each:每个元素重复的次数
seq, seq_len, seq_along # 连续数字组成的向量 seq 创建序列，seq(from, to, by) by是步长默认是1 seq_along(along.with) 根据along.with的长度n创建序列 seq_len(n) 根据n创建长度为n的序列
rev
sample
choose, factorial, combn
(is/as).(character/numeric/logical/...)

# 列表和数据框
list, unlist
data.frame, as.data.frame
split
expand.grid

# 控制流
if, &&, || (short circuiting)
for, while
next, break
switch
ifelse # ifelse(test, yes, no) test为真，输出yes值，否则输出no值。

# apply函数和相似函数
lapply, sapply, vapply
apply
tapply
replicate # replicate(n, f) # 对于函数f运行n次
```
<!-- more -->
### 常见数据结构
```
# 日期时间
ISOdate, ISOdatetime, strftime, strptime, date 
difftime # difftime(date1, date2) 返回时间差
julian, months, quarters, weekdays # weekdays(date) 返回星期几 # quarters() 返回季度 # moths() 返回月份 # julian(date) 返回date离19700101的天数
library(lubridate)

# 字符处理
grep, agrep
gsub # 字符替换 gsub(pattern, replacement, x)
strsplit
chartr
nchar
tolower, toupper
substr
paste # paste(data1, data2, sep = "world") 结果是data1和data2拼接中间以world连接，world是可以自己定义的
library(string)

# 因子
factor, levels, nlevels
reorder, relevel
cut, findInterval
interaction
options(stringAsFactors = FALSE)

# 数组处理
array
dim
dimnames
aperm
library(abind)
```

### 统计函数
```
# 排序和制表
duplicated, unique  # unique 找出不同的元素
merge
order, rank, quantile
sort
table, ftable

# 线性模型
fitted, predict, resid, restandard
lm, glm
hat, influence.measures
logLik, df, deviance
formula, ~, I
anova, coef, confint, vcov
contrasts

# 测试类函数
apropos("\\.test$")

# 随机变量
(q, p, d, r) * (beta, binom, cauchy, chisq, exp, f, gamma, geom, hyper, lnorm, logis, multinom, nbinom, norm, pois, signrank, t, unif, weibull, wilcox, birthday, tukey)

# 矩阵运算
crossprod, tcrossprod
eigen, qr, svd
%*%, %o%, outer # a%*%b 求矩阵a和矩阵b的积
rcond
solve # solve(a,b) a矩阵，b向量或矩阵 求a%*%x=b的x，若不指定，则求a的逆矩阵
```

### 使用R
```
# 工作空间
ls, exists, rm # ls: 当前工作空间中的objects # exists 判断是否存在当前工作空间 # rm 删除工作空间中某个object
getwd, setwd # 返回当前工作空间 # 设置当前工作空间
q # 退出
source # "预装"函数,向R脚本导入其他函数并运行
install.packages, library, require 

# 帮助
help, ?
help.search
apropos
RSiteSearch
citation
demo
example
vignette

# 调试
traceback
browser
recover
options(error = )
stop, warning, message
traCath, try
```

### I/O函数
```
# 输出
print, cat
message, warning
dput
format
sink, capture.output

# 读／写数据
data
count.fields
read.csv, write.csv
read.delim, write.delim 
read.fwf 
readLines, writeLines
readRDS, saveRDS
load, save 
library(foreign)

# 文件和目录
dir
basename, dirname, tools::file_ext
file.path
path.expand, normalizePath
file.choose
file.copy, file.create, file.remove, file.rename, dir.create
file.exists, file.info
tempdir, tempfile
download.file, library(downloader)

```

## 查看帮助
```
help 或 ? :调用帮助系统

help.search 或 ??: 搜索包含指定字符串的文档

example: 运行帮助页面中的Example部分

help.start: 现实包含R系统帮助的html页面
```

## NA处理函数
na.fail(object, ...) # 若object中包含NA，则失败
na.omit(object, ...) # 若object中包含NA，则排除
na.exlude(object, ...) # 若object中包含NA，则排除，这与na.omit一样。但使用naresid napredeitct的函数中，通过NA排除的行再次添加到结果
na.pass(object, ...) # 即使object含有NA值，也使之通过

## 参考文献
[require和library](https://stackoverflow.com/questions/5595512/what-is-the-difference-between-require-and-library)
《R语言与数据分析》