---
title: "hexo 安装第一篇"           #可以随意修改,可以是中文
categories: blog                    #文章文类
date: 2017-01-12 23:23:41
tags: [小章鱼, hexo]                 #文章tag标签,多个标签用逗号隔开
---

### 第一步
安装 node
[node](https://nodejs.org/en/)

### 第二步
安装 git
[git](https://git-scm.com/)

### 第三部
安装  hexo 
`$ npm install -g hexo-cli`

<!-- more -->

### 第四步
创建hexo文件夹
'hexo init'
这里有一个坑的地方在于使用的使npm安装的初始theme的时候很慢，你耐心等待就好了

### 第五步
安装hexo依赖
`npm install`

### 第六步
创建hexo文件夹所在目录执行
`hexo g`
`hexo s`
可以在localhost：4000访问到页面
这里有一个坑的地方是如果以上步骤都对的话，如果访问4000端口没有页面，那就你就是安装了福新阅读器，不要问我问什么知道
执行`hexo s -p 5000`

本地的介绍到这里

---
参考链接
[hexo官网](https://hexo.io/zh-cn/docs/setup.html)
[博客](http://blog.csdn.net/u012246342/article/details/51543370)