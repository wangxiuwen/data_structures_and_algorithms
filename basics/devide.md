# 分治 && 回溯

代码模版

```python
def devide_conquer(problem, param1, param2, ...):
  # recursion terminator
  if problem is None:
    print_result
    return
  
  # prepare data
  data = prepare_data(problem)
  subproblems = split_problem(problem, data)

  # conquer subproblems
  subresult1 = self.devide_conquer(subproblems[0], p1, ...)
  subresult2 = self.devide_conquer(subproblems[1], p1, ...)
  subresult3 = self.devede_conquer(subproblems[2], p1, ...)

  ...

  # process and generate the final result
  result = process_result(subresult1, subresult2, subresult3, ...)

  # revert the current level states
```



# leetcode

[22. 括号生成](https://leetcode-cn.com/problems/generate-parentheses/)
[50. Pow(x, n)](https://leetcode-cn.com/problems/powx-n/)