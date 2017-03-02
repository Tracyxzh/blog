---
title: java 算法 （搜索算法 二分排序）
categories: 算法                    #文章文类
date: 2017-02-28 20:30:19
tags: ["小章鱼", "java", "algorithm"]
---

## 二分搜索算法

二分搜索算法顾名思义就是每次分成两边的搜索算法，这个算法的要求是数据已经是排序过的数据。

步骤
* 排序
* 比较中值和搜索值大小，化分搜索范围
* 对划分的范围继续搜索

```
/*
* 不是迭代的二分搜索算法
 */
public static int binarySearch(int[] arr, int low, int high,int search) {
    System.out.println("");
    while (low <= high) {
        int mid = (low + high) / 2;
        if (search > arr[mid]) {
            low = mid + 1;
            System.out.println("mid: " + mid + "high: " + high + "low: " + low);
        } else if (search < arr[mid]) {
            high = mid - 1;
            System.out.println("mid: " + mid + "high: " + high + "low: " + low);
        } else {
            System.out.println("找到的数据在第" + mid + "值为：" + arr[mid]);
            return arr[mid];
        }
    }
    System.out.println("无此数据");
    return -1;
}

/*
* 二分迭代搜索算法
 */
public static int binaryItratorSearch(int[] arr, int low, int high, int search) {
    System.out.println("");
    if (low <= high) {
        int mid = (low + high) / 2;
        if (search < arr[mid]) {
            high = mid -1;
            System.out.println("mid: " + mid + "high: " + high + "low: " + low);
            binaryItratorSearch(arr, low, high, search);
        } else if (search > arr[mid]) {
            low = mid + 1;
            System.out.println("mid: " + mid + "high: " + high + "low: " + low);
            binaryItratorSearch(arr, low, high, search);
        } else {
            System.out.println("找到的数据在第" + mid + "值为：" + arr[mid]);
            return arr[mid];
        }
    }
    System.out.println("无此数据");
    return -1;
}
```