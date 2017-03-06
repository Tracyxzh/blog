---
title: java 算法 （排序算法 快速排序）
categories: 算法                    #文章文类
date: 2017-02-24 13:44:19
tags: ["小章鱼", "java", "algorithm"]
---

ps:今天听了一首感动死我的歌，歌曲名是Bressanone（布列瑟农），听的时候全身鸡皮疙瘩都起来了，然后我就去搜这首歌，谁知道还有一个感人的故事。
以下是作者自述，链接来着一个音乐推荐网站
[音乐链接](http://music.163.com/#/song/1696822?userid=109343852)
<!-- more -->

## 快速排序（Quick Sort）
听着音乐差点都忘记了主题了，这篇blog的主题是快速排序。

思想：快速排序由C.A.R.Hoare （1962）开发的，算是分治算法的一种。该算法在数组中选择一个主元（pivot）的元素将数组分为两部分，使得第一部分中所有元素都小于或等于主元，而第二部分中的所有元素都大于主元。对第一第二部分递归调用。
步骤：
* 取pivot
* 划分两部分
* 递归调用划分方法

具体代码
```
/*
* 快速排序
*/
public static void quickSort(int[] arr) {
    System.out.println("");
    System.out.println("快速排序前的数组为： ");
    for (int i : arr) {
        System.out.print(i + " ");
    }
    quickSort(arr, 0, arr.length - 1);
    System.out.println("");
    System.out.println("快速排序后的数组为：");
    for (int i : arr) {
        System.out.print(i + " ");
    }
}

private static void quickSort(int[] arr, int first, int last) {
    if (last > first) {
        int pivot = partition(arr, first, last);
        quickSort(arr, first, pivot - 1);
        quickSort(arr, pivot + 1, last);
    }
}

private static int partition(int[] arr, int first, int last) {
    int pivot = arr[first]; // 主元
    int low = first + 1;
    int high = last;
    while (high > low) {
        while (low <= high && arr[last] <= pivot) {
            low++;
        }
        while (low <= high && arr[high] > pivot) {
            high--;
        }
        if (high > low) {
            int temp = arr[high];
            arr[high] = arr[low];
            arr[low] = temp;
        }
    }
    while (high > first && arr[high] >= pivot) {
        high--;
    }
    if (pivot > arr[high]) {
        arr[first] = arr[high];
        arr[high] = pivot;
        return high;
    } else {
        return first;
    }
}

```

```
马修·连恩—布列瑟农

谢谢你的评论，现在给你自己冲杯热茶，坐好，我接下来给你说个关于bressanone的故事......

几年前，我疯狂地爱上了一个年轻的女孩，还有，也爱上了南部蒂罗尔山区，它在意大利的北部，与奥地利接壤，就在勃伦尔山脉的南边（勃伦尔山脉正好把意大利和奥地利分隔开来）。

南部蒂罗尔曾经跟北部蒂罗尔（现在属于奥地利）和西部蒂罗尔（现在属于瑞士）是一个整体。这个地区的人说的是德国的一种方言，但是由于蒂罗尔被分割开来，而南部蒂罗尔变成意大利的一部分，所以这里的地名一般都有意大利文和德文两种名字。

总之呢...许多年前我给绿色和平组织工作，在那时候我遇上了一个让我心动的女孩子。我们是在加州的约塞米蒂国家公园归途中相遇的。自那以后，她回到科罗拉多州的绿色和平组织，最后回到纽约洲去上学，而我则回到圣迭戈的绿色和平组织，并且最后回到我在加拿大育空地区的老家。

此后的几个月里我们不停地通讯。很快我们都希望能有更进一步的发展。她将要去意大利的佛罗伦萨学习艺术，我就要去德国的慕尼黑开始新的表演生活，跟一支叫“三月粉”的摇滚乐队...哈啊，没错，三月粉...那是另外一个故事了。

当我俩都在欧洲的时候，我们选了一个处在佛罗伦萨和慕尼黑之间的地方约会。这就是南部蒂罗尔的一个小镇，德文里面它叫“Brixen”，意大利文就是“bressanone”。Bressanone是个非常优美的小镇。它被小乡村包围着，而山谷中回响着教堂的钟声，山羊在牧场漫步，远处是高耸的白色山头。

我们在那里玩乐了几天，探索过周围的小乡村，还有彼此的心。离别的日子到了，她要回去的时候我陪着她去附近乡村的火车站，真是很令人沮丧啊，我们都要踏上各自的道路。流着泪水，我上了去火车站的公共汽车，在短短的40分钟路程里，我缓缓入睡了，在梦中，我隐隐约约地似乎听到了这样的一首歌，非常美妙的旋律和歌词。我醒来的时候，赶紧下了车，来到最近的咖啡店，把所听到的旋律和歌词写在一张餐巾纸上，好让我能够永远地记住它。

一年以后，我才有机会把这首歌录下来。在我的心里，永远会留个地方是给她，还有那些小乡村，和这首歌。

谢谢你这么认真地听我说。现在...是时候跟你同睡了，晚安!!!

:-)

马修

附原文：

The Story

by Matthew Lien

Date: 02-20-02 18:10

Hello Forrest,

Thank you for your comments. Now make yourself a cup of hot tea, sit back, and I'll tell you a story about Bressanone...

Several years ago, I fell deeply in love with a young woman, and also with a part of northern Italy known as South Tyrol. It borders Austria, just south of the Brenner mountain pass which separates Italy from Austria.

South Tyrol used to be joined with North Tyrol (now a part of Austria) and West Tyrol (now a part of Switzerland). The people of this area speak a dialect of German. But since Tyrol was divided and South Tyrol became a part of Italy, all the place names are in both German and Italian.

Anyway... I once worked for Greenpeace many years ago, where I met a young woman who melted my heart. We met while on a retreat in California's Yosemite National Park. After the retreat, she returned to the Colorado Greenpeace office, and eventually went back to school in New York state. I returned to the San Diego Greenpeace Office, and eventually went back to my home in the Yukon, Canada.

Over the months we stayed in touch. Soon we discovered that we would both be close again. She was going to study art in Florence, Italy, and I was going to live in Munich, Germany performing with a rock band called "Marching Powder"... ahhhh yes, Marching Powder... but that's another story.

When we were both in Europe, we made arrangements to meet in a place that was close to being between Florence and Munich. This was the South Tyrolian town called "Brixen" in German, or "Bressanone" in Italian. Bressanone is a beautiful town surrounded by small villages high in the mountain valleys with churches ringing and sheep in the meadows, and the awesome peaks of the Dolomite mountains towering beyond.

We spent several days exploring the mountain villages and each other's hearts. And when the day came for her to return, I took her to a train station in a nearby village, and we said goodbye. It was very sad to be going our own ways again. With tears in my eyes, I got on a bus and headed for the train station in Bressanone. During the short 40-minute bus ride, I fell asleep. And while I slept, I had a dream in which I could hear this song, complete with the words and music. When I awoke, I got off the train and went to the nearest coffee shop to write the words and music on a napkin, so I would not forget.

It was years later when I finally recorded the song. I will always have a place in my heart for her... and for that village... and for this song.

Thank you for listening. Now... off to bed with you!!!

:-)

Matthew
```
## 参考链接
[故事](http://www.sanwen.net/subject/3704574/)