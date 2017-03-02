---
title: java 面试遇到的问题
date: 2017-02-28 12:56:15
categories: java                    #文章文类
tags: [小章鱼, java, 学习笔记, 面试]
---

前言：突然发现我现在写blog喜欢写些原因，最近有可能是在图书馆听着民谣，效率更高吧。我写这个就是想着把自己面试遇到的一些小问题整理下，方便自己以后看看，以方便以后别人面试的时候遇到。

## java 初始化块、静态初始化块、构造函数初始化
[理解Java中的类初始化](https://www.caoqq.net/java-class-initialization.html)

## static 关键字
* 当声明一个事物为static时，就意味着这个域或方法不会与包含它的类的任何对象实例关联在一起。
* 即使从未创建某个类的任何对象，也可以调用其static方法或访问其static域

<!--more-->

## equals 和 ==
在Object中，使用equals方法和使用“==”运算符是完全等价的，不过许多类重写了Object类的equals方法，String类也是如此。重写后比较的是值而不是地址。

注意：
* String类是不可变的，String类一旦创建久不可改变。
* String类采用字符串常量池是合理的，因为String是非可变的，即使多个引用指向同一个String对象，也不会导致一份对象改变影响另外的对象。
* 使用String类的场景：在字符串不经常变化的场景中可以使用String类，例如常量的声明、少量的变量运算。
* 使用StringBuffer类的场景：在频繁进行字符串运算（如拼接、替换、删除等），并且运行在多线程环境中，则可以考虑使用StringBuffer，例如XML解析、HTTP参数解析和封装。
* 使用StringBuilder类的场景：在频繁进行字符串运算（如拼接、替换、和删除等），并且运行在单线程的环境中，则可以考虑使用StringBuilder，如SQL语句的拼装、JSON封装等。

## public static void main(String[] args)
这样定义的原因
* public main方法在程序启动的时候有jvm调用，所以应声明为public
* static 静态方法，方法被调用，要么使用对象实例引用访问，要么声明为static，使用类直接调用。main方法声明为static这样就无需生成对象实例，直接使用jvm调用。
* void 无返回类型
* String[] args 用户输入参数

## java 8种基本数据类型
* byte    字节型  8位
* char    字符型  16位
* short   短整型  16位
* int     整型    32位
* long    长整型  64位
* float   浮点型  32位
* double  双浮点型  64位
* boolean 布尔型    true false

## 包装类 拆装箱问题
java中的基本数据类型不是对象，因为这些数据使用简便，如果作为对象处理，每次使用都需要在堆上分配空间，然后在不需要的时候由垃圾回收器来清理，会照成很大的资源浪费。

解决的是将基本数据类型和包装类的转换。
```
HashMap<String, Integer> map = new HashMap<String, Integer>(); // HashMap<String, int> map = new HashMap<String, int>(); 会报错误
map.put("test1", 11);
map.put("test2", 12);

for (Map.Entry<String, Integer> entry : map.entrySet()) {
    System.out.println("key:" + entry.getKey() + " value:" + entry.getValue());
}

long t = System.currentTimeMillis();
Long sum = 0L;
for (long i = 0; i < Integer.MAX_VALUE; i++) {
    sum += i;
}
System.out.println("total:" + sum);
System.out.println("processing time: " + (System.currentTimeMillis() - t) + " ms");

long t1 = System.currentTimeMillis();
long sum1 = 0L;
for (long i = 0; i < Integer.MAX_VALUE; i++) {
    sum1 += i;
}
System.out.println("total:" + sum1);
System.out.println("processing time: " + (System.currentTimeMillis() - t1) + " ms");
```

## java 流
流向：
* 输入流：
* 输出流：
* 字节流：
* 字符流：
* 节点流：
* 过滤流：


[blog](http://blog.oneapm.com/apm-tech/635.html)

## 参考资料
《java编程思想》
《细说java》
[jdk8](http://docs.oracle.com/javase/8/docs/api/index.html)
[知乎](https://www.zhihu.com/question/20101840)