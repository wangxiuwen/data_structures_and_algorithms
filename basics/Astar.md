# A* search

## 估价函数

启发式函数: h(n)，它用来评价哪些结点最有希望的是一个我们要找的结 点，h(n) 会返回一个非负实数,也可以认为是从结点n的目标结点路径的估 计成本。
启发式函数是一种告知搜索方向的方法。它提供了一种明智的方法来猜测 哪个邻居结点会导向一个目标。


## 代码模版

```python
def AstartSearch(graph, start, end):
    pq = collections.priority_queue() # 优先级 --> 估价函数
    pq.append([start])
    visited.add(start)

    while pq:
        node = pq.pop() # can we add more intelligence here?
        visited.add(node)

        process(node)

        nodes = generate_related_nodes(node)
        
        unvisited = [node for node in nodes if node not in visited]
        pq.push(unvisited)
```

## leetcode 例题

[1091. 二进制矩阵中的最短路径](https://leetcode-cn.com/problems/shortest-path-in-binary-matrix/)
[773. 滑动谜题](https://leetcode-cn.com/problems/sliding-puzzle/) 
[37. 解数独](https://leetcode-cn.com/problems/sudoku-solver/)