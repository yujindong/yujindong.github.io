---
title: InsertSort
date: 2016-07-18 23:45:17
categories:
  - Algorithm
tags:
  - 排序
  - SORT
---

# 插入排序
## 定义
插入排序是一种简单直观的排序算法。它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。插入排序在实现上，通常采用in-place排序（即只需用到O(1)的额外空间的排序），因而在从后向前扫描过程中，需要反复把已排序元素逐步向后挪位，为最新元素提供插入空间。
## 实现
### 插入排序 ts实现
```ts
function insertSort(arr: number[]): number[] {
  if(arr.length <= 1) {
    return arr;
  }
  const len = arr.length;
  for (let i = 1; i < len; i++) {
    // 从第i个元素开始向前比较，如果小于前一个元素，交换位置
    for (let j = i; j > 0 && arr[j] < arr[j - 1]; j--) {
      swap(arr, j, j - 1);
    }
  }
  return arr;
}
function swap(arr: number[], i: number, j: number) {
  [arr[i], arr[j]] = [arr[j], arr[i]];
}
```
### 插入排序 js实现
```js
function insertSort(arr) {
  if(arr.length <= 1) {
    return arr;
  }
  const len = arr.length;
  for (let i = 1; i < len; i++) {
    // 从第i个元素开始向前比较，如果小于前一个元素，交换位置
    for (let j = i; j > 0 && arr[j] < arr[j - 1]; j--) {
      swap(arr, j, j - 1);
    }
  }
  return arr;
}
function swap(arr, i, j) {
  [arr[i], arr[j]] = [arr[j], arr[i]];
}
```