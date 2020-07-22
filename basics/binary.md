# 二分查找


- 目标函数单调性(单调递增或者递减)
- 存在上下界(bounded)
- 能够通过索引访问(index accessible)


## 代码模版

### 循环

```python
left, right = 0, len(array) -1
while left <= right:
  mid = (left+right)/2
  if array[mid] == target:
    # find the target
    break or return result
  elif array[mid] < target:
    left = mid + 1 # 左右下界为整型需要加一减一，左右下界如果为实数则直接等于 mid 即可
  else:
    right = mid - 1
```

```Java
public int bsearch(int[] a, int n, int value) {
  int low = 0;
  int high = n - 1;

  while(low < high) {
    int mid = (low+high)/2;
    if(a[mid] == value) {
      return mid;
    } else if (a[mid] > value) {
      high = mid - 1;
    } else {
      low = mid + 1;
    }
  }
  return -1;
}
```

### 递归

```Java
public int bsearch(int[]a, int n, int val) {
  return bearchInternally(a, 0, n - 1, val);
}

private int bsearchInternally(int[] a, int low, int high, int value) {
  int mid = low + (high -  low) >> 1;
  if(a[mid] == value) {
    return mid;
  } else if (a[mid] < value) {
    return bsearchInternally(a, mid+1, high, value);
  } else {
    return bsearchInternally(a, low, mid-1, value);
  }
}
```

## 示例

在递增数组里面 [10,14,19,26,27,31,33,35,42,44]

查找 31


## leetcode 

[69. x 的平方根](https://leetcode-cn.com/problems/sqrtx/)  
[33. 搜索旋转排序数组](https://leetcode-cn.com/problems/search-in-rotated-sorted-array/)

