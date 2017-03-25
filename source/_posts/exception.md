---
title: java 异常
date: 2017-03-22 16:06:42
tags: [java, Exception]
---

## 前言
印象中对于，异常的了解就只是try，catch，然后用的比较多的几乎是Exception。以前学习的时候想的就是只要能用会用就好了，没怎么关注过异常，还以为Exception是所有异常的基类。昨天做了大众点评的实习笔试，发现自己理心仪的大众点评还是有一些差距的，笔试中关于异常的题目，自己都不是很了解。所以，今天就来探讨下java的异常和错误。

## Throwable类
Throwable类是java语言中所有错误和异常的基类，用来描述违例抛出的东西。Throwable有两种常规规范，Error和Exception。

## Exception和Error
Error 代表编译期和系统错误，我们一般不必特意捕获它们（除在特殊情况以外）。Exception 是可以从任何标准 Java库的类方法中“掷”出的基本类型。此外，它们亦可从我们自己的方法以及运行期偶发事件中“掷”出。在Java中我们可以这样区分，异常(Exception)是一种非程序原因的操作失败(Failure)，而错误(Error)则意味着程序有缺陷(Bug)。

<!--more-->

## 构造函数
```
Exception的构造函数，Error和和他一样。
public Exception() {
    super();
}


public Exception(String message) {
    super(message);
}

public Exception(String message, Throwable cause) {
    super(message, cause);
}


public Exception(Throwable cause) {
    super(cause);
}
Trowable主要的方法 public void printStackTrace() { printStackTrace(System.err);}
将此 throwable 及其追踪输出至标准错误流。此方法将此 Throwable 对象的堆栈跟踪输出至错误输出流，作为字段 System.err 的值。输出的第一行包含此对象的 toString() 方法的结果。剩余行表示以前由方法 fillInStackTrace() 记录的数据。
```
## RuntimeException
RuntimeException 是那些可能在 Java 虚拟机正常运行期间抛出的异常的超类。Java中区分Checked Exception和Unchecked Exception，前者继承于Exception，后者继承于RuntimeException。上面的IOException就是一个著名的Checked Exception。Java编译器对Checked Exception的约束包括两方面：对于方法编写者来讲，Checked Exception必须在方法签名上声明；对于方法调用者来讲，调用抛出Checked Exception的方法必须用try-catch捕获异常或者继续声明抛出。相反，Unchecked Exception则不需要显式声明，也不强制捕获。

Checked Exception的用意在于明确地提醒调用者去处理它，防止遗漏。但是Checked Exception同时也给调用者带来了负担，通常会导致层层的try-catch，降低代码的可读性，前面例子中的Integer.valueOf方法虽然声明了NumberFormatException，但是它是一个RuntimeException，所以使用者不是必须用try-catch去捕获它。

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=5223019&auto=1&height=66"></iframe>

## 参考链接
[java 编程思想](http://www.java17.cn/Javabased/26.html)
[jdk](http://download.java.net/jdk/jdk-api-localizations/jdk-api-zh-cn/builds/latest/html/zh_CN/api/)
[博客](http://www.cnblogs.com/weidagang2046/p/exception-handling-principles.html)