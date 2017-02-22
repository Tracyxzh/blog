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