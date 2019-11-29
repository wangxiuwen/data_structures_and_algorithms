# 刷题技巧

## outliers

- Chunk it up 切碎知识点
- Deiliberate practicing 刻意练习  
        
```
过遍数(五) 
刷题第一遍 5～15分钟思考
直接看解法，多解法的比较解法优劣
刷题第四遍/第五遍 的时候一定要上英文站 discuss board 中 查看 Most Votes 中最高票的前三个回答
练习缺陷，弱点的地方  
不舒服，不爽，枯燥  
生活中的例子： 乒乓球，台球，玩游戏等
```

- Feed back 获得反馈  
  
  主动型反馈 (自己去找)  
    
```
高手代码  
    github  
    Solution from leetcode, discuss pannel in leetcode
```
  
  被动型反馈  
    
```
code review  
教练看你打，给你反馈
```


## 切题四件套

- clarification 明确数据范围
- Possible Solution 所有可能选最优
- compare(time/space)
- optimal(加强)


## 数据结构

一维:

- 基础： 
    
    数组 array(string) 链表 linked list
- 高级： 
    
    栈 stack， 队列 queue， 双端队列（deque）， 集合（set），映射 map (hash or map), etc

二维:

- 基础： 
    
    树 tree， 图 graph

- 高级： 
    
    二叉搜索树 binary search tree（red-black tree, AVL）, 堆 heap， 并查集 disjoint set， 字典树 Trie， etc

特殊：

- 位运算 Bitwise， 布隆过滤器(BloomFilter)
- LRU Cache

## 算法

- if-ele, switch --> branch
- for, while loop --> iteration
- 递归 Recursion(Divide & Conquer, Backrace)
- 搜索 Search 深度优先搜索 Depth first search， 广度优先搜索 Breadth first search, A*, etc
- 动态规划 Dynamic Programming
- 二分查找 Binary Search
- 贪心 Greedy
- 数学 Math， 几何 Geometry

>注意：  
    在头脑中回忆上面没种算法的思想和代码模版

## 编辑器

### vscode

安装 leetcode plugin

top tips vscode/vscode 使用技巧

|  功能   | 快捷键  |
|  ----  | ----  |
| 打开快捷键一览表 | `ctrl k + ctrl s` |
| 跳到行尾/首  | `command + left/right` |
| 选中整行 | `shift+ cmd + left/right` |
| 删除一行  | `cmd + shift + k`/ `cmd+x` |
| 删除光标前面一个单词  | `option+delete` |

### idea

|  功能   | 快捷键  |
|  ----  | ----  |
| 显示意向动作和快速修复代码  | `Option + Enter` |
| 显示最近打开的文件记录列表 | `command + E` |




## 自顶向下的编程方式

<https://markhneedham.com/blog/2008/09/15/clean-code-book-review/>

关键的函数放上面，子函数放下面

## 练习重点

动态规划，搜索，回溯，递归


## 优化的思路

空间换时间  
升维


## 懵逼的时候

找最近重复子问题
