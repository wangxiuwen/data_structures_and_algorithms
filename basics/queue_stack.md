# 队列和栈

## 查看文档方式

google： queue java 10

## Priority Queue 优先队列

1. 插入操作： O(1)
2. 取出操作： O(log n) 按照元素优先级取出
3. 底层具体实现数据结构较为复杂： heap, bst(二叉搜索树，平衡二叉搜索树(比如说红黑树或者 AVL))，treap

[Java 的 PriorityQueue 文档](https://docs.oracle.com/javase/10/docs/api/java/util/PriorityQueue.html)
[Java 的 Stack 源码](http://developer.classpath.org/doc/java/util/Stack-source.html)
[Java 的 Queue 源码](http://fuseyism.com/classpath/doc/java/util/Queue-source.html)
[Python 的 heapq](https://docs.python.org/2/library/heapq.html)
[高性能的 container 库](https://docs.python.org/2/library/collections.html)

## 复杂度

[bigocheatsheet](https://www.bigocheatsheet.com/)


## 小结

1. stack, queue, Deque 的原理和操作复杂度
2. PriorityQueue 的特点和操作复杂度
3. 查询 Stack, Queue, Deque, Priority Queue 的系统接口的方法