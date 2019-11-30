# 队列

队列跟栈一样，也是一种操作受限的线性表数据结构 
用数组实现的队列叫作 `顺序队列`，用链表实现的队列叫作 `链式队列`
最基本的操作有两个：入队enqueue()，放一个数据到队列尾部；出队dequeue()，从队列头部取一个元素  


## 循环队列 

高性能队列Disruptor、Linux环形缓存，都用到了循环并发队列；Java concurrent并发包利用ArrayBlockingQueue来实现公平锁


## 阻塞队列


## 并发队列



## 查看文档方式

google： queue java 10

## Priority Queue 优先队列

1. 插入操作： O(1)
2. 取出操作： O(log n) 按照元素优先级取出
3. 底层具体实现数据结构较为复杂： heap, bst(二叉搜索树，平衡二叉搜索树(比如说红黑树或者 AVL))，treap

[Java 的 PriorityQueue 文档](https://docs.oracle.com/javase/10/docs/api/java/util/PriorityQueue.html)  
[Java 的 Queue 源码](http://fuseyism.com/classpath/doc/java/util/Queue-source.html)  
[Python 的 heapq](https://docs.python.org/2/library/heapq.html)  
[高性能的 container 库](https://docs.python.org/2/library/collections.html)  

## 复杂度

[bigocheatsheet](https://www.bigocheatsheet.com/)

## 小结

1. queue, Deque 的原理和操作复杂度
2. PriorityQueue 的特点和操作复杂度
3. 查询 Queue, Deque, Priority Queue 的系统接口的方法


## leetcode

20,155,232,844,224,682,496