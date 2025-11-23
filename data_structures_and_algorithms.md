# 数据结构与算法

## 数据结构

## 经典算法

### 排序算法

<https://www.runoob.com/w3cnote/sort-algorithm-summary.html>

1. 冒泡排序：

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

### 缓存算法
