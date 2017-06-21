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
all.equal, identical
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
&, |, !, xor
all, any
intersect, union, setdiff, setequal
which

# 向量与矩阵
c, matrix
# 强制转换规则字符型(character)>数值型(numeric)逻辑型(logical)
length, dim, ncol, nrow
cbind, rbind
names, colnames, rownames
t
diag
sweep
as.matrix, data.matrix

# 构建向量
c
rep, rep_len
seq, seq_len, seq_along
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
ifelse

# apply函数和相似函数
lapply, sapply, vapply
apply
tapply
replicte
```
<!-- more -->
### 常见数据结构
```
# 日期时间
ISOdata, ISOdatatime, strftime, strptime, data
difftime
julian, months, quarters, weekdays
library(lubridate)

# 字符处理
grep, agrep
gsub
strsplit
chartr
nchar
tolower, toupper
substr
paste
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
duplicated, unique
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
%*%, %o%, outer
rcond
solve
```

### 使用R
```
# 工作空间
ls, exists, rm # ls: 当前工作空间中的objects # exists 判断是否存在当前工作空间 # rm 删除工作空间中某个object
getwd, setwd # 返回当前工作空间 # 设置当前工作空间
q # 退出
source # "预装"函数
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

## 参考文献
[require和library](https://stackoverflow.com/questions/5595512/what-is-the-difference-between-require-and-library)