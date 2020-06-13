# 分治 && 回溯

代码模版

```python
def divide_conquer(problem, param1, param2, ...):
  # recursion terminator
  if problem is None:
    print_result
    return
  
  # prepare data
  data = prepare_data(problem)
  subproblems = split_problem(problem, data)

  # conquer subproblems
  subresult1 = self.divide_conquer(subproblems[0], p1, ...)
  subresult2 = self.divide_conquer(subproblems[1], p1, ...)
  subresult3 = self.divide_conquer(subproblems[2], p1, ...)

  ...

  # process and generate the final result
  result = process_result(subresult1, subresult2, subresult3, ...)

  # revert the current level states
```

## 技巧

1. 人肉递归低效、很累
2. 找到最近最简方法，将其拆解成可重复解决的问题
3. 数学归纳法思维(抵制人肉递归的诱惑)

>本质: 寻找重复性 -> 计算机指令集

# leetcode

[22. 括号生成](https://leetcode-cn.com/problems/generate-parentheses/)
[50. Pow(x, n)](https://leetcode-cn.com/problems/powx-n/)