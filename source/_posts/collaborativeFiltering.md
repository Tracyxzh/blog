---
title: 协同过滤
date: 2017-06-06 21:50:11
tags: [数据挖掘, 算法]
---

## 前言
最近在实习数据挖掘的工作，但是做的事情就是将oracle的存储过程改成spark sql，这里坦白下我的Scala还在学习的路上。但是我的学习习惯是刨根问底，数据挖掘最终用到的算法才是最终吸引我的。而且最近真的喜欢用网易云听歌，一边听着JBL中放着的歌，一边看着算法，想象自己喝着红酒🍷。所以今天看看推荐算法是如何实现的。

## 协同过滤 collaborative filtering
之所以称为“协同”是因为该方法基于其他用户进行推荐。实际上，人们通过协同合作来形成推荐。其工作流程如下：假设要完成的任务是推荐一本书。那么会在网站上搜索与你兴趣类似的其他用户。一旦找到这个用户，就看看这个用户所喜欢的书然后将它们推荐给你。
找到相似用户的方法一般是通过距离。
距离一般化：明氏距离（Minkowski Distance）
$$b(x,y)=(\sum\_{k=1}^{n} |x\_{k}-y\_{k}|)^{r^{1/r}}$$
其中：
* r=1时，上述公式计算的就是曼哈顿距离
* r=2时，上述公式计算的就是欧式距离
* r=3时，上述公式计算的是上确界距离

缺点：r越到，某一维较大差异对最终差值的影响越大。

曼哈顿距离函数
```
def manhattan(rating1, rating2):
    """Computes the Manhattan distance. Both rating1 and rating2 are dictionaries
       of the form {'The Strokes': 3.0, 'Slightly Stoopid': 2.5}"""
    distance = 0
    commonRatings = False 
    for key in rating1:
        if key in rating2:
            distance += abs(rating1[key] - rating2[key])
            commonRatings = True
    if commonRatings:
        return distance
    else:
        return -1 #Indicates no ratings in common
```

pearson 相关系数
```
def pearson(self, rating1, rating2):
        sum_xy = 0
        sum_x = 0
        sum_y = 0
        sum_x2 = 0
        sum_y2 = 0
        n = 0
        for key in rating1:
            if key in rating2:
                n += 1
                x = rating1[key]
                y = rating2[key]
                sum_xy += x * y
                sum_x += x
                sum_y += y
                sum_x2 += pow(x, 2)
                sum_y2 += pow(y, 2)
        if n == 0:
            return 0
        # now compute denominator
        denominator = (sqrt(sum_x2 - pow(sum_x, 2) / n)
                       * sqrt(sum_y2 - pow(sum_y, 2) / n))
        if denominator == 0:
            return 0
        else:
            return (sum_xy - (sum_x * sum_y) / n) / denominator
```

余弦相似度
```
def dot_product(v1, v2):
    return sum(a * b for a, b in zip(v1, v2))
def similarity(v1, v2):
    return dot_product(v1, v2) / (magnitude(v1) * magnitude(v2) + .00000000001)
```

相似度选择：
* 如果数据受到分数贬值（即不同用户使用不同的评价范围）的时候，使用皮尔逊系数
* 如果数据稠密（几乎所有都没有零值）且属性值大小十分重要，那么可以使用欧氏距离或者曼哈顿距离
* 如果数据稀疏，考虑使用余弦相似度

<!-- more -->

## 参考书籍和链接
《写给程序员的数据挖掘》
[书籍](http://guidetodatamining.com/)
[博客](http://www.cnblogs.com/luchen927/archive/2012/02/01/2325360.html)
[知乎](https://www.zhihu.com/question/19971859)

## 每文音乐推荐
评论：
草莓味的咸鱼：顾城有一首叫作《避免》的诗
“你不愿意种花
你说：
'我不愿看见它
一点点凋落'
是的
为了避免结束
你避免了一切开始”
觉得和塞林格的《破碎故事之心》异曲同工之秒
is a touch and yet not a touch
想触碰却又收回手

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=36307219&auto=1&height=66"></iframe>