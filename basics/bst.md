# 深度优先搜索和广度优先搜索

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

## DFS 非递归写法

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

## Java DFS 层序遍历

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

## 其它资料

[AlphaZero Explained](https://nikcheerla.github.io/deeplearningschool/2018/01/01/AlphaZero-Explained/)  
[棋类复杂度](https://en.wikipedia.org/wiki/Game_complexity)