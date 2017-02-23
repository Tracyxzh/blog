---
title: java 算法 （排序算法 冒泡排序）
date: 2017-02-23 23:02:39
categories: java                    #文章文类
tags: [小章鱼, java, 算法]
---
 
 ## 题外话
 ps:今天真的是被git弄的稀里糊涂了一天，弄到现在还在实验室，我都怀疑自己的认真劲头了😂。
 以前觉得自己没有做技术的耐性，无法静静的呆在自己的电脑前。那个时候坐在电脑前都会流眼泪，那个时候就对自己说：是的我不合适做技术，然而读研的路上感觉自己的性格改变了很多，不敢说非常踏实，但是目前来说，静静地看着技术文档和书籍，常常能获得快感，就像现在已经过了12点，我在“奋笔疾书”。解决bug的时候有那么一丝丝成就感，不知道是不是自己越来越适合做技术了，感觉自己每天过的越来越充实和快乐，只要今天的自己比昨天的自己更强大。

## 正题
* 排序算法 分类
	* 交换排序
		* 冒泡排序
		* 快速排序
	* 选择排序
		* 选择排序
		* 堆排序
	* 插入排序
		* 插入排序
		* shell排序
	* 合并排序

#### 冒泡排序（Bubble Sort）
思想：冒泡排序需要遍历多遍数组，在每次遍历🀄比较相邻的元素。较小值像“气泡”一样上浮，较大的值沉向底部。
步骤：
* 对数组中的各个数据，依次比较相邻的两个数据大小
* 如果前面的数据大于后面的数据，就交换两个数据。这样可以找出最小的。
* 依次用同样的方法，排序。
时间：$\dfrac {n\left( n-1\right) } {2}=O\left( n^{2}\right)$

```
主要代码：
package sort;

import UtilAlgorithm.Main;
import UtilAlgorithm.Util;

/**
 * Created by xiezhanghua on 2017/2/23.
 */
public class Sort {
    public static int[] bubleSort(int[] arr) {
        System.out.println("冒泡排序前的数组为：");
        for (int i : arr) {
            System.out.print(i + " ");
        }

        for (int i = 1; i < arr.length; i++) {
            for (int j = 0; j < arr.length - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
        System.out.println("");
        System.out.println("冒泡排序后的数组为：");
        for (int i : arr) {
            System.out.print(i + " ");
        }
        return arr;
    }
}
```


 ## 参考书籍和链接
 《java 常用算法手册》
 《java 语言程序设计》
