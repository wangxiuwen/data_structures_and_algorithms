#   并查集 Disjoint Set

## 适用场景

- 组团、配对问题
- Group or not ?


## 基本操作

- makeSet(s):建立一个新的并查集，其中包含 s 个单元素集合。
- unionSet(x, y):把元素 x 和元素 y 所在的集合合并，要求 x 和 y 所在的集合不相交，如果相交则不合并。
- find(x):找到元素 x 所在的集合的代表，该操作也可以用于判断两个元 素是否位于同一个集合，只要将它们各自的代表比较一下就可以了。

## 代码模版

```Java
class UnionFind {
    private int count = 0;
    private int[] parent;

    public UnionFind(int n) {
        count = n;
        parent = new int[n];
        for (int i = 0; i < n; i++) {
            parent[i] = i;
        }
    }

    public int find(int p) {
        while (p != parent[p]) {
            parent[p] = parent[parent[p]];
            p = parent[p];
        }
        return p;
    }

    public void union(int p, int q) {
        int rootP = find(p);
        int rootQ = find(q);
        if (rootP == rootQ) return;
        parent[rootP] = rootQ;
        count--;
    }
}
```

```python
def init(p):
# for i=0 ..n:p[i]=i;
p=[i for i in range(n)]
def union(self,p,i,j):
    p1=self.parent(p,i)
    p2=self.parent(p,j)
    p[p1]=p2

def parent(self,p,i):
    root=i
    while p[root]!=root:
        root=p[root]
    while p[i]!=i: # 路径压缩?
        x=i;i=p[i];p[x]=root
    return root
```