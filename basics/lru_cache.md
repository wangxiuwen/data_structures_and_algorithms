# LRU Cache


## python 使用 LRU Cache

```
from functools import lru_cache
@lru_cache(None)
def add(x, y):
  return x+y
```


## 参考资料

<https://www.jianshu.com/p/b1ab4a170c3c>  

[Understanding the Meltdown exploit](https://www.sqlpassion.at/archive/2018/01/06/understanding-the-meltdown-exploit-in-my-own-simple-words/)    
[缓存文件置换机制](https://en.wikipedia.org/wiki/Cache_replacement_policies)  
[缓存文件置换机制 中文](https://zh.wikipedia.org/wiki/快取⽂文件置換機制)  

## leetcode

[146. LRU缓存机制](https://leetcode-cn.com/problems/lru-cache/)
