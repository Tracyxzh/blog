---
title: 逻辑回归
date: 2017-06-28 10:07:50
tags: [logical, 机器学习]
---

## 前言
最近在做一个早期预警的模型，这个模型用到了逻辑回归，这里记录下自己学习逻辑回归的笔记。

## sigmod函数推导
逻辑回归用到sigmod函数作为概率模型，相信很多人在一开始看机器学习相关书籍的时候就看到了，但是为什么可以用sigmod函数作为概率模型还有很多疑惑。这里首先讲解下为什么可以用sigmod函数作为概率模型。其实机器学习的核心也就是要找到一个概率模型和找到损失函数，然后使得损失函数最小不断地改进系数。下图是sigmod的推导，手写字有点难看😂
![sigmod推导](logicalRegssion/sigmod.jpeg)

<!--more-->

## 决策函数
一个机器学习的模型，实际上把决策函数限定在某一组条件下(也就是特征)，这组限定条件决定了模型的假设空间。

## 损失函数
![损失函数](logicalRegssion/loss.jpeg)


## 参考链接
[美团技术](http://tech.meituan.com/intro_to_logistic_regression.html)
[博客](http://blog.csdn.net/YoYoDelphine/article/details/52888276)
[知乎](https://www.zhihu.com/question/30643044)
[edu](http://ufldl.stanford.edu/wiki/index.php/Softmax%E5%9B%9E%E5%BD%92#.E4.B8.AD.E8.8B.B1.E6.96.87.E5.AF.B9.E7.85.A7)
[softmax](https://zhuanlan.zhihu.com/p/21485970)