---
title: oracle 内置函数
date: 2017-06-03 11:06:39
tags: [oracle, 数据库]
---

## 写在前面的话
由于有的时候需要对于字符串或则日期使用一些内置的函数，但是平时google的时候也比较麻烦，这里干脆做个记录，方便以后自己翻阅。

## 数值函数
* ABS(n) 取绝对值
* MOD(n2, n1) 取n2除以n1的余数
* SIGN(n) 返回参数n的符号。1 0 -1

## 三角函数
* COS(n) n为弧度
* ACOS(n)
* SIN(n)
* TAN(n)

## 指数／对数函数
* SQRT(n) n的平方根
* POEWR(n2,n1) n2的n1次幂
* EXP(n) e的n次幂
* LOG(n1, n2) n1位底的n2对数

## 四舍五入函数
* ROUND(n，integer) 四舍五入精确到小数点的integer位
* TRUNC(n， integer) 截取到小数点的integer位

## 字符函数 参数都是字符类型的参数单引号
LENGTH(char) 返回指定的字符长度


<!--- more -->
### 字符串截取 
参数(char,position[,substring_length]) 
char：原始字符串
position：要截取字符串的开始位置
substring_length：截取的长度
SUBSTR：以字符为单位
SUBSTRB：以字节为单位
SUBSTRC：以unicode为单位
SUBSTR2：以UCS2代码点为单位
SUBSTR4：以UCS4代码点为单位

### 字符串连接函数
CONCAT(char1,char2)函数 效果与“||”相似

### 字符串搜索函数
参数(string,substring[,position[,occurrence]])
string：待搜索的字符串
substring：要搜索的字符串
position：搜索开始的位置,默认是1
occuurrence：substring第几次出现，默认是1
INSTR：以字符为单位
INSTRB：以字节为单位
INSTRC：以unicode为单位
INSTR2：以UCS2代码点为单位
INSTR4：以UCS4代码点为单位

### 字母大小转换函数
UPPER(char)
LOWER(char)
INITCAP(char) 所有单词首字母大写

### 替换字符函数
REPLACE(char,serch_string[,replace_string])
char: 表示搜索的目标字符串
search_string: 在目标中要搜索的字符串
replace_string: 该参数可选，不填的话就是删除搜索的字符串

### 字符串的填充
RPAD(expr1,n[,expr2]) 
功能： 在字符串expr1的右边用字符串expr2填充，不填写expr2的话，就用空格填充
LPAD(expr1,n[,expr2])
功能： 在字符串expr1的左边用字符串expr2填充，不填写expr2的话，就用空格填充

### 删除字符串首尾指定字符的函数
TRIM([LEADING|TRAILING|BOTH][trim_character FROM] trim_source)
LEADING：删除trim_source的前缀字符
TRAILING：删除trim_source的后缀字符
trim_character：删除指定的字符，默认删除空格
trim_source：被操作的字符串

## 日期函数
### 系统时间
SYSDATE SYSTIMESTAMP

### 数据库时区函数
DBTIMEZONE

### 为日期加上指定月份函数
ADD_MONTHS(data,integer) 
功能： 该函数返回指定的日期加上一个月份数后的日期

## 转换函数
ASCIISTR(char) 将任意字符集的字符串转换为数据库字符集对应的ASCII字符串
CAST(expr as type_name) 把expr参数转换成type_name类型

### 数值转换成字符串函数
参数(n,[,fmt[,nlsparam]])
n: 数值或者日期
fmt：要转换的格式
TO_CHAR(number)
TO_CHAR(data)

### 字符串转日期函数
TO_DATA(char[,fmt[,nlsparam]])
char:待转换的字符
fmt：表示转换的格式
nlsparam：控制格式化时使用的语言类型



### 每文音乐推荐
评论：
无心廿曰：我懒到连喜欢的人，都懒的换
菮煕：还是老妈说的话最经典，她说：“你们这代人呐，就是活的太明白了，所以什么都得不到。我们当年什么都糊里糊涂，该结婚结婚，该工作工作，现在什么都有。”

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=1615656&auto=1&height=66"></iframe>













