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

<!--more-->

## matlab 
语法：imshow ( f, G) 
      imshow (f, [low high])
      imshow (f, [ ])
说明：G是显示该图像的灰度级数；
      小于或等于low的值都显示为黑色，大于或等于high的值都显示为白色。
          [ ]自动将变量low设置为f的最小值，将high设置为f的最大值。

## idea 技巧
快速生成
```
public static void main(Sting[] agrs) {
  
}
```
解决方法：在idea中输入psvm，然后按tab就可以自动生成

快速生成
```
System.out.println();
```
解决方法：在idea中输入sout，然后按tab就可以自动生成

快速生成构造函数
```
class Dog {
    String name;
    String says;
   <!--  public Dog(String name, String says) {
        this.name = name;
        this.says = says;
        这里被注释掉的是构造函数，如果快速生产
    } --> 
}
```
解决方法： 在idea中选择code->generator 或者直接按下control+n（Mac环境下）

## 参考链接
[blog1](http://www.cnblogs.com/sword-successful/p/6408281.html)
<!-- more -->
## hexo 中写数学公式 Latex

ps:今天本来是准备动手看算法方面的东西，然后准备使用hexo看下数学公式怎么显示。然后就出现问题了，显示的时候会出现很多莫名的问题。重要的是我都没有数学编辑器，😂话说论文也要写了啊。所以开始找个好一点的数学编辑器，然后在b呼中找到了。那么问题来了，是时候写一篇练习Latex的文档了。

[submlim + Latex](https://www.zhihu.com/question/23918126/answer/29977055)
[b呼推荐](https://www.zhihu.com/question/20928639)
[解决方法](http://draveness.me/hexozhong-latexde-shi-yong/)：就是把主题中的配置文件中的 mathjax: true 设置为true

## 一些小概念
语法糖(Syntactic sugar)：是由Peter J. Landin(和图灵一样的天才人物，是他最先发现了Lambda演算，由此而创立了函数式编程)创造的一个词语，它意指那些没有给计算机语言添加新功能，而只是对人类来说更“甜蜜”的语法。

brew 和 brew cask
brew是从下载源码解压然后./configure && make install,同时会包含相关依赖库。并自动配置好各种环境变量，而且易于卸载。

brew cask 是已经编译好的应用包，仅仅是下载解压，放在统一的目录中（/opt/homebrew-cask/Caskroo,），省掉了自己去下载 解压 安装步骤。

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=27731391&auto=1&height=66"></iframe>