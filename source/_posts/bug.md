---
title: 开发中的bug
categories: bug
date: 2017-02-22 13:40:48
tags: [bug, 小章鱼, hexo]
---

问题：解决maven 更新慢的问题
系统：Mac
解决方向：使用阿里镜像
方法：
1. cd /usr/local/Cellar/maven/3.3.9/libexec/conf(brew install maven 的路径)
2. subl setting.xml (subl 在这里是使用sublime text 打开 文件 open -a )
3. 将下面代码替换setting.xml中的 mirrors	
```
<mirrors>
  <!-- mirror
   | Specifies a repository mirror site to use instead of a given repository. The repository that
   | this mirror serves has an ID that matches the mirrorOf element of this mirror. IDs are used
   | for inheritance and direct lookup purposes, and must be unique across the set of mirrors.
   |
  <mirror>
    <id>mirrorId</id>
    <mirrorOf>repositoryId</mirrorOf>
    <name>Human Readable Name for this Mirror.</name>
    <url>http://my.repository.com/repo/path</url>
  </mirror>
   -->
  <mirror>
    <id>alimaven</id>
    <name>aliyun maven</name>
    <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
    <mirrorOf>central</mirrorOf>       
  </mirror>
</mirrors>
```

## 参考链接
[blog1](http://www.cnblogs.com/sword-successful/p/6408281.html)
<!-- more -->
## hexo 中写数学公式 Latex

ps:今天本来是准备动手看算法方面的东西，然后准备使用hexo看下数学公式怎么显示。然后就出现问题了，显示的时候会出现很多莫名的问题。重要的是我都没有数学编辑器，😂话说论文也要写了啊。所以开始找个好一点的数学编辑器，然后在b呼中找到了。那么问题来了，是时候写一篇练习Latex的文档了。

[submlim + Latex](https://www.zhihu.com/question/23918126/answer/29977055)
[b呼推荐](https://www.zhihu.com/question/20928639)
[解决方法](http://draveness.me/hexozhong-latexde-shi-yong/)：就是把主题中的配置文件中的 mathjax: true 设置为true