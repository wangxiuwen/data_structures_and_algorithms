#  Bloom Filter

## Bloom Filter vs Hash Table
    
    一个很长的二进制向量和一系列随机映射函数。
    布隆过滤器可以用于检索一个元素是否在一个集合中。
    优点是空间效率和查询时间都远远超过一般的算法，缺点是有一定的误识别率和删除困难。


## 案例

    1. 比特币网络
    2. 分布式系统(Map-Reduce) — Hadoop、search engine
    3. Redis 缓存
    4. 垃圾邮件、评论等的过滤

## 科普

<https://www.cnblogs.com/cpselvis/p/6265825.html>
<https://blog.csdn.net/tianyaleixiaowu/article/details/74721877>


## Python 实现

```python
from bitarray import bitarray
import mmh3

class BloomFilter:

    def __init__(self, size, hash_num): # hash_num 指一个元素被映射多少个二进制位
        self.size = size
        self.hash_num = hash_num 
        self.bit_array = bitarray(size) 
        self.bit_array.setall(0)
        
    def add(self, s):
        for seed in range(self.hash_num):
            result = mmh3.hash(s, seed) % self.size 
            self.bit_array[result] = 1
    
    def lookup(self, s):
        for seed in range(self.hash_num):
            result = mmh3.hash(s, seed) % self.size 
            if self.bit_array[result] == 0:
                return "Nope" 
        return "Probably"

bf = BloomFilter(500000, 7) 
bf.add("dantezhao")
print (bf.lookup("dantezhao")) 
print (bf.lookup("yyj"))
```

## 其他实现

1. Python: 

<https://www.geeksforgeeks.org/bloom-filters-introduction-and-python-implementation/>    
<https://github.com/jhgg/pybloof>

2. Java: 

<https://github.com/lovasoa/bloomfilter/blob/master/src/main/java/BloomFilter.java>  
<https://github.com/Baqend/Orestes-Bloomfilter>


## 其它链接

[布隆过滤器的原理和实现](https://www.cnblogs.com/cpselvis/p/6265825.html)  
[使用布隆过滤器解决缓存击穿、垃圾邮件识别、集合判重](https://blog.csdn.net/tianyaleixiaowu/article/details/74721877)  
[布隆过滤器 Python 代码示例](https://shimo.im/docs/xKwrcwrDxRv3QpKG/)  
