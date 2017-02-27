---
title: nginx
date: 2017-02-27 15:29:54
categories: nginx                    #文章文类
tags: [小章鱼, nginx, 学习笔记]
---

前段时间买了一个阿里云服务器，由于是学生特价，还挺实惠的。然后过年期间就一直没去弄他，备案也差最后照相没去弄，找个时间把这个弄了。所以想着可以玩玩服务器，这段时间没怎么接错linux方面的知识，刚好借助这个机会熟悉下。拿到服务器，开始的时候是一脸萌比的，里面什么都没有，所以需要自己安装相应的软件。

## 第一步 远程登录
[参考blog](http://blog.geeek.info/2016/03/18/linux%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%AE%89%E5%85%A8%E8%AE%BE%E7%BD%AE/)
[阿里帮助文档](https://help.aliyun.com/knowledge_detail/41493.html)
使用iterm2 在本地配置好了，就可以ssh免密登陆到阿里云服务器了。

## 第二步 安装 nginx

步骤
```
* yum -y install nginx
* /etc/init.d/nginx start 
这个地方会报错，nginx：nginx: [emerg] socket() [::]:80 failed (97: Address family not supported by protocol)
解决方案： 
	* vim /etc/nginx/conf.d/default.conf
	* 注释 [::]:80 default_server
* /etc/init.d/nginx restart
* 访问ip
```
<!--more-->
## 第三步，nginx 配置文件构成

```
......
events
{
......
}

https
{
......
	server
	{
	......
	}

	server
	{
	......
	}	
......
}
```


## 第四步 nginx 压缩输出配置

```
gzip on 开启gzip模块
gzip_buffers number size 设置系统获取几个单位的缓存用于存储gzip的压缩结果数据流。
gzip_min_length 设置允许压缩的页面最小字节流，建议大于1K压缩。
gzip_http_version 1.0| 1.1 是别http版本
gzip_proxied [off|expired|no-cache|no-store...] nginx作为反向代理的时候启用开启或关闭后端服务器返回的结果。
gzip_type mime-type 匹配mime类型进行压缩

demo
http
{
include conf/mime-type;

gzip on;
gzip_min_length 1000;
gzip_buffers 4 8K;
gzip_http_version 1.1;
gzip_type text/plain application/x-javascript text/css text/html application/xml;

......
}
```

## 第五步 nginx 的浏览器本地缓存设置
```
location ~ .*/.(git | jpg | jpeg | png | bmp | sef)$
{
	expires 30d;
}
location ~ .*/.(js | css)?$
{
	expires 1h;
}
```

## 参考资料
《实战Nginx》
《Nginx Http server》