# 数据结构与算法

## 数据结构

## 经典算法

### 排序算法

<https://www.runoob.com/w3cnote/sort-algorithm-summary.html>

1. 冒泡排序
    时间复杂度 ~ O(N^2)

    ```cpp
    void bubble_sort(vector<int> & arr) {
    //每次冒泡后，最后的元素最大，处理剩余的数组
    for (int res_size = arr.size() ; res_size > 0; res_size--) {
        //遍历剩余的数组，如果当前元素与后一个元素相比更大，交换两者位置
        for (int i = 0 ; i < res_size - 1 ; i++) {
            if (arr[i] > arr[i+1]) {
                int tmp = arr[i];
                arr[i] = arr[i+1];
                arr[i+1] = tmp;
            }
        }
    }
    return ;
    }
    ```

2. 堆排序
3. 快排
    avg 时间复杂度 ~ O(NlogN)
    worst 时间复杂度 ~ O(N^2)
    best 时间复杂度 ~ O(NlogN)

    详细阅读 <https://zh.wikipedia.org/wiki/%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F>

    两种实现思路：

    1. 用标记位分割左右两个数组，最后和标记位元素进行连接，需要额外开辟两个数组占用的
    O(N) 的空间

        ```text
        function quicksort(q)
        {
            var list less, pivotList, greater
            if length(q) ≤ 1 
                return q
            else 
            {
                select a pivot value pivot from q
                for each x in q except the pivot element
                {
                    if x < pivot then add x to less
                    if x ≥ pivot then add x to greater
                }
                add pivot to pivotList
                return concatenate(quicksort(less), pivotList, quicksort(greater))
            }
        }
        ```

    2. in-place 方式，直接对标记位左边的数组 & 右边的数组进行复用，通过移动元素的方式实现分割

        ```text
        function partition(a, left, right, pivotIndex)
            {
                pivotValue = a[pivotIndex]
                swap(a[pivotIndex], a[right]) // 把pivot移到結尾
                storeIndex = left
                for i from left to right-1
                {
                    if a[i] < pivotValue
                    {
                        swap(a[storeIndex], a[i])
                        storeIndex = storeIndex + 1
                    }
                }
                swap(a[right], a[storeIndex]) // 把pivot移到它最後的地方
                return storeIndex
            }
        procedure quicksort(a, left, right)
            if right > left
                select a pivot value a[pivotIndex]
                pivotNewIndex := partition(a, left, right, pivotIndex)
                quicksort(a, left, pivotNewIndex-1)
                quicksort(a, pivotNewIndex+1, right)
        ```

### 缓存算法
