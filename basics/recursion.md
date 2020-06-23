# 递归

去的过程叫“递”，回来的过程叫“归”  
写递归代码的关键就是找到如何将大问题分解为小问题的规律，并且基于此写出递推公式，然后再推敲终止条件，最后将递推公式和终止条件翻译成代码  
编写递归代码的关键是，只要遇到递归，我们就把它抽象成一个递推公式，不用想一层层的调用关系，不要试图用人脑去分解递归的每个步骤  

递归与循环没有明显的边界，它是通过函数体来进行的循环

## 界定问题能否用递归解决

- 一个问题的解可以分解为几个子问题的解
- 这个问题与分解之后的子问题，除了数据规模不同，求解思路完全一样
- 存在递归终止条件


## 编写递归代码的技巧

终止条件
递推公式


## 注意的点

- 警惕堆栈溢出

>递归会利用栈保存临时变量，如果递归过深，会造成栈溢出。解决方案是控制递归的深度

- 警惕重复计算

> 递归要警惕重复计算，递归分解的子问题、子子问题可能存在相同的情况，如果都一一计算的话，就会发生重复计算。解决方案是使用散列表来保存结算结果，每次开始计算前检查散列表是否已经有结算结果 


## 递归优化

笼统地讲，递归代码都能用迭代循环来替换  

## 递归一般流程

```
1. terminator
2. process current logic
3. drill down
4. 恢复当前层
```

## python 代码模版

```python
def recursion(level, param1, param2,...):
  # recuision terminator 递归终结条件
  if level > MAX_LEVEL:
    process_result
    return
  
  # process logic in current level 处理当前层逻辑
  process(level, data...)

  # drill down 下探到下一层
  self.recursion(level+1, p1,...)

  # reverse the current level status if needed 清理当前层
```


## Java 代码模版

```java
public void recur(int level, int param) {
  // terminator
  if (level > MAX_LEVEL) {
    // process result
    return
  }

  // process current logic
  process(level, param)

  // drill down
  recur(level:level+1, newParam)

  // restore current status
}
```

## DFS 递归写法

```python
visited = set()

def dfs(node, visited):
  # 1. terminator
  if node in visited:
    return

  visited.add(node)

  # process_current_logic
  ...

  for next_node in node.children():
    if not next_node in visited:
      dfs(next_node, visited) 
```

## DFS 递归写法

```python
def dfs(self, root):
    if not root:
      return
    
    visited, stack = [], [root]

    while stack:
      node = stack.pop()
      visited.add(node)

      process(node)

      nodes = generate_related_nodes(node)
      stack.push(nodes)

    # other processing work

```

## BFS 代码

```python
def bfs(self, root):
  if not root:
    return
  
  visited, queue = [], [root]

  while queue:
    node = queue.pop()
    visited.add(node)

    process(node)
    
    nodes = generate_related_nodes(node)
    queue.push(nodes)
```

## Java 的写法

```Java
public List<List<Integer>> levelOrder(TreeNode root) {
  List<List<Integer>> allResults = new ArrayList<>();
  if (root == null) {
      return allResults;
  }
  travel(root, 0, allResults);
  return allResults;
}


private void travel(TreeNode root, int level, List<List<Integer>> results) {
  if (results.size() == level) {
      results.add(new ArrayList<>());
  }
  results.get(level).add(root.val);
  if (root.left != null) {
      travel(root.left, level + 1, results);
  }
  if (root.right != null) {
      travel(root.right, level + 1, results);
  }
}
```


## 思维要点

- 不要人肉递归
- 找到最近重复子问题
- 数学归纳法思维


## leetcode 题目

[22.括号生成](https://leetcode-cn.com/problems/generate-parentheses/)
[70.爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/)