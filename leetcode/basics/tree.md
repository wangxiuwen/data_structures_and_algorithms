# 树

## 二叉树


## 树和图的差别

看是否有环，有环为图


## 示例代码

Python

```python
class TreeNode:
  def __init__(self, val):
    self.val = val
    self.left, self.right = None, None
```

C++

```c++
struct TreeNode {
  int val;
  TreeNode *left;
  TreeNode *right;
  TreeNode (int x): val(x), left(NULL), right(NULL) {}
}
```

Java

```java
  public int val;
  public TreeNode left, right;
  public TreeNode (int val) {
    this.val = val;
    this.left = null;
    this.right = null
  }
```


## 二叉树的遍历

1.前序(Pre-order): 根-左-右
2.中序(In-order): 左-根-右
3.后序(Post-order): 左-右-根

### 遍历示例代码

```python
def preorder(self, root):
  if root:
    self.traverse_path.append(root.val)
    self.preorder(root.left)
    self.preOrder(root.right)

def inorder(self, root):
  if root:
    self.inorder(root.left)
    self.traverse_path.append(root.val)
    self.inorder(root.right)

def postorder(self, root):
  if root:
    self.postorder(root.left)
    self.postorder(root.right)
    self.traverse_path(root.val)

```

## 二叉搜索树

二叉搜索树，也称为二叉搜索排序树、有序二叉树(Ordered Binary Tree)、排序二叉树(Sorted Binary Tree), 是指一棵空树
或者具有下列性质的二叉树：

1. 左子树上 `所有节点` 的值均小于它的根节点的值
2. 右子树上 `所有节点` 的值均大于它的根节点的值
3. 依次类推：左、右子树也分别为二叉查找树(这就是 重复性！)

中序遍历：升序排列


## 问题

树的面试题一般都是递归的，这是为什么？
