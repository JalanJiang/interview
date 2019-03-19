## 归并排序(Merge Sort)

### 复杂度

时间复杂度：`O(nlogn)`

### 原理

- 把长度为 n 的输入序列分成两个长度为 n/2 的子序列
- 对这两个子序列分别采用归并排序
- 将两个排序好的子序列合并成一个最终的排序序列

![归并排序](/img/algorithm/sort/merge-sort.md.gif)

### 实现

```python
def merge_sort(lst):
    if len(lst) <= 1:
        return lst          # 从递归中返回长度为1的序列

    middle = len(lst) / 2
    left = merge_sort(lst[:middle])     # 通过不断递归，将原始序列拆分成n个小序列
    right = merge_sort(lst[middle:])
    return merge(left, right)

def merge(left, right):
    i, j = 0, 0
    result = []
    while i < len(left) and j < len(right):  # 比较传入的两个子序列，对两个子序列进行排序
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    result.extend(left[i:])         # 将排好序的子序列合并
    result.extend(right[j:])
    return result
```

## 参考资料

- [python 归并排序](https://www.cnblogs.com/webber1992/p/6142527.html)