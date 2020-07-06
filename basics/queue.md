# 队列

队列跟栈一样，也是一种操作受限的线性表数据结构 
用数组实现的队列叫作 `顺序队列`，用链表实现的队列叫作 `链式队列`
最基本的操作有两个：入队enqueue()，放一个数据到队列尾部；出队dequeue()，从队列头部取一个元素  


## 循环队列 

高性能队列Disruptor、Linux环形缓存，都用到了循环并发队列；Java concurrent并发包利用ArrayBlockingQueue来实现公平锁

![](./queue/queue.jpg)

- 在用数组实现的非循环队列中，队满的判断条件是tail == n，队空的判断条件是head == tail
- 循环队列队列为空的判断条件 head == tail
- 循环队列队满时 (tail+1)%n=head

## 阻塞队列

阻塞队列其实就是在队列基础上增加了阻塞操作。简单来说，就是在队列为空的时候，从队头取数据会被阻塞。因为此时还没有数据可取，直到队列中有了数据才能返回；如果队列已经满了，那么插入数据的操作就会被阻塞，直到队列中有空闲位置后再插入数据，然后再返回。


## 并发队列

线程安全的队列我们叫作并发队列。最简单直接的实现方式是直接在enqueue()、dequeue()方法上加锁，但是锁粒度大并发度会比较低，同一时刻仅允许一个存或者取操作。实际上，基于数组的循环队列，利用CAS原子操作，可以实现非常高效的并发队列。这也是循环队列比链式队列应用更加广泛的原因。

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


## 延伸

[无锁队列的实现](https://coolshell.cn/articles/8239.html)

## 源码阅读

- Java queue
- Java deque
- Java priority queue(取出：O(logn), 插入O(1))

vector 是线程安全的， ArrayList 不是

## 思考

- 用栈模拟队列 --> 用两个栈
- 用队列模拟栈 
