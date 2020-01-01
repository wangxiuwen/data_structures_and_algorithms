# 哈希表

哈希表(hash table)， 也叫散列表，是根据关键码值(key value) 而直接进行访问的数据结构
它通过贝把关键码值映射到表中的一个位置来访问记录，以加快查找的速度。
这个映射函数叫做散列函数(hash function)，存放记录的数组叫做哈希表(或散列表)


Map: key - value对，key不重复
```java
new HashMap()/ new TreeMap()
map.set(key, value)
map.get(key)
map.has(key)
map.size()
map.clear()
```

Set： 不重复元素集合

```java
new HashSet()/ new TreeSet()
set.add(value)
set.delete(value)
set.hash(value)
```

> python 中 map 为 `dict`， set 是 `set`


## 源码阅读

- Java hash set
- Java hash map(hash node, tree node, 看懂put、get)

## leetcode

```
242
```