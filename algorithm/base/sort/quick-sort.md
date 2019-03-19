## 快速排序(Quick Sort)

- LeetCode 习题：[75. 颜色分类](https://leetcode-cn.com/problems/sort-colors/)

### 时间复杂度

时间复杂度并不固定，如果在最坏情况下（元素刚好是反向的）速度比较慢，达到 `O(n^2)`（和选择排序一个效率），但是如果在比较理想的情况下时间复杂度 `O(nlogn)`。

### 原理

![快速排序](/img/algorithm/sort/quick-sort.gif)

### 实现

```python
class Solution(object):
    def sortColors(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        self.quickSort(nums, 0, len(nums)- 1)
        
    def quickSort(self, nums, left, right):
        # 结束递归的条件
        if left > right:
            return 
        
        i = left
        j = right
        tmp = nums[i]
        
        while i != j:
            # 先判断 j 再判断 i，从末尾开始
            # 递增或递减条件：j > i
            while nums[j] >= tmp and j > i:
                j = j - 1
            while nums[i] <= tmp and j > i:
                i = i + 1
            # 交换条件：j > i
            if j > i:
                t = nums[i]
                nums[i] = nums[j]
                nums[j] = t
        
        # 交换基准数
        nums[left] = nums[i]
        nums[i] = tmp
        
        self.quickSort(nums, left, i - 1)
        self.quickSort(nums, i + 1, right)
        
```