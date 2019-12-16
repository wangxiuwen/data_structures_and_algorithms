# 二分查找


- 目标函数单调性(单调递增或者递减)
- 存在上下界(bounded)
- 能够通过索引访问(index accessible)


## 代码模版

```python
left, right = 0, len(array) -1
while left <= right:
  mid = (left+right)/2
  if array[mid] == target:
    # find the target
    break or return result
  elif array[mid] < target:
    left = mid + 1
  else:
    right = mid - 1
```

## 示例

在递增数组里面 [10,14,19,26,27,31,33,35,42,44]

查找 31


## leetcode 

[69. x 的平方根](https://leetcode-cn.com/problems/sqrtx/)

[33. 搜索旋转排序数组](https://leetcode-cn.com/problems/search-in-rotated-sorted-array/)

