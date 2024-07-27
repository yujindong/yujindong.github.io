---
title: SelectionSort
date: 2016-07-18 23:44:10
categories:
  - Algorithm
tags:
  - 排序
  - SORT
---

## 选择排序
### 定义
选择排序是一种简单的排序算法，它的工作原理是每次从未排序的部分中选择最小的元素，将其放到已排序部分的末尾。具体来说，选择排序会重复地遍历待排序序列，一次比较两个元素，如果它们的顺序错误就把它们交换过来。遍历序列的工作是重复进行的，直到没有再需要交换的元素为止。

选择排序的时间复杂度为O(n^2)，其中n是序列的长度。虽然这种排序算法在某些情况下可能不是最优的，但由于其简单易懂的实现方式，它仍然在一些特定的应用场景中被广泛使用。

## 实现
### 选择排序 ts实现
```ts
function selectionSort(arr: number[]): number[] {
  if(arr.length <= 1) {
    return arr;
  }
  const len = arr.length;
  for (let i = 0; i < len; i++) {
    // 找到未排序部分的最小元素索引
    let minIndex = i;
    for (let j = i + 1; j < len; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }
  }
  return arr;
}

function swap(arr: number[], i: number, j: number) {
  [arr[i], arr[j]] = [arr[j], arr[i]];
}

```

### 选择排序 js实现
```js
function selectionSort(arr) {
  if(arr.length <= 1) {
    return arr;
  }
  const len = arr.length;
  for (let i = 0; i < len; i++) {
    // 找到未排序部分的最小元素索引
    let minIndex = i;
    for (let j = i + 1; j < len; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }
    // 将最小元素与当前位置的元素交换
    swap(arr, i, minIndex);
  }
  return arr;
}
function swap(arr, i, j) {
  [arr[i], arr[j]] = [arr[j], arr[i]];
}
```

### 选择排序的java实现
```java
  public class SelectionSort {
    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        selectionSort(arr);
        System.out.println("排序后的数组：");
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
    }

    public static void selectionSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            // 找到未排序部分的最小元素索引
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
            // 将最小元素与当前位置的元素交换
            swap(arr, i, minIndex);
        }
    }

    public static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}
```

