## 二分查找

LeetCode 练习题：[704. 二分查找](https://leetcode-cn.com/problems/binary-search/)

### 思想

二分查找只适用顺序存储结构。

将查找的键和子数组的中间键作比较，如果被查找的键小于中间键，就在左子数组继续查找；如果大于中间键，就在右子数组中查找，否则中间键就是要找的元素。

### 代码

```python
class Solution(object):
    def search(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        i = 0
        j = len(nums) - 1
        while i <= j:
            mid = (i + j) // 2
            if nums[mid] == target:
                return mid
            else:
                if nums[mid] > target:
                    j = mid - 1
                else:
                    i = mid + 1
        return -1
```

### 变种

#### 查找第一个与 target 相等的元素

#### 查找最后一个与 target 相等的元素

#### 查找最后一个等于或者小于 target 的元素

#### 查找最后一个小于 target 的元素

#### 查找第一个等于或者大于 target 的元素

#### 查找第一个大于 target 的元素

#### 变种总结

## 参考资料

- [[算法总结] 二分查找](https://www.jianshu.com/p/0f823fbd4d20)