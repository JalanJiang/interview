## 冒泡排序

- LeetCode 习题：[75. 颜色分类](https://leetcode-cn.com/problems/sort-colors/)

### 复杂度

- 最好：`O(n)`
- 最坏：`O(n^2)`
- 平均：`O(n^2)`

### 原理

核心思想：比较相邻元素并交换

![冒泡排序](/img/algorithm/sort/bubble-sort.gif)

### 实现
 
```python
class Solution(object):
    def sortColors(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        length = len(nums)
        i = 0
        j = i + 1
        while length > 0:
            while j < length:
                if nums[i] > nums[j]:
                    tmp = nums[i]
                    nums[i] = nums[j]
                    nums[j] = tmp
                i = i + 1
                j = j + 1
            length = length - 1
            i = 0
            j = i + 1
```