## 堆排序(Heap Sort)

- LeetCode 习题：[215. 数组中的第K个最大元素](https://leetcode-cn.com/problems/kth-largest-element-in-an-array/)

### 复杂度

- 时间复杂度：`O(nlogn)`
- 空间复杂度：`O(1)`

### 原理

![堆排序](/img/algorithm/sort/heap-sort.gif)

### 实现

```python
class Solution(object):
    def findKthLargest(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        length = len(nums)
        # 构建大顶堆
        for i in reversed(range(0, length / 2)):
            self.adjustHeap(nums, i, length)

        count = 0
        for j in reversed(range(0, length)):
            count = count + 1
            if count == k:
                return nums[0]
            self.swap(nums, 0, j)
            length = length - 1
            self.adjustHeap(nums, 0, length)


    def adjustHeap(self, nums, i, length):
        while True:
            k = i * 2 + 1 #left node
            if k >= length:
                return
            if k + 1 < length and nums[k+1] > nums[k]:
                k = k + 1
            if nums[k] > nums[i]:
                self.swap(nums, i, k)
                i = k
            else:
                return

    def swap(self, nums, i, j):
        temp = nums[i]
        nums[i] = nums[j]
        nums[j] = temp
```

