# trie 树


字典树，即 Trie 树，又称单词 查找树或键树，是一种树形结构。典型应用是用于统计和排序大量的字符串(但不仅限于字符串)，所以经常被搜索引擎系统用于文本词频统计。
它的优点是:最大限度地减少无谓的字符串比较，查询效率比哈希表高。

## 基本性质

1. 根节点不包含字符，除根节点外每个节点都只包含一个字符或不包含字符，结点本身不存完整单词;
2. 从根结点到某一结点，路径上经过的字符连接起来，为该结点对应的字符串;
3. 每个结点的所有子结点路径代表的字符都不相同。

## 核心思想

Trie 树的核心思想是空间换时间。 利用字符串的公共前缀来降低查询时间的开销以达到提高效率的目的。

## 代码模版

```Java
static final int ALPHABET_SIZE = 256;
static class TrieNode {
    TrieNode[] children = new TrieNode[ALPHABET_SIZE];
    boolean isEndOfWord = false;
    TrieNode () {
        isEndOfWord = false;
        for (int i = 0; i < ALPHABET_SIZE; i++) {
            children[i] = null;
        }   
    }
}
```

```python
# TrieNode:
def __init__(self):
    self.children = [None] * ALPHABET_SIZE

    # isEndOfWord is True if node represent
    # the end of the word
    self.isEndOfWord = False
```

