# 字符串

两个字符串变换问题，一般要转成一个二维数组，两个字符串分别为字符串的行和列


## 定义及常见操作

[string immutable](https://lemire.me/blog/2017/07/07/are-your-strings-immutable/)

python:

```python
x = 'abbc'
for ch in x: 
    print(ch)
```

Java:

```Java
String x = "abbc";
String y = "abbc";

for (int i = 0; i < x.length(); ++i) {
    char ch = x.charAt(i);
}
for (char ch : x.toCharArray()) {
    System.out.println(ch);
}

if (x.equals(y)) System.out.println("x==y");
if (x.equalsIgnoreCase(y)) System.out.println("x==y equalsIgnoreCase");
```

```c++
#include <iostream>

using namespace std;

int main() {
    string s("abbc");
    for (int i = 0; i < s.length(); i++) {
        cout << s[i];
    }
}
```

###  字符串 + 递归 or DP

https://leetcode-cn.com/problems/regular-expression-matching/

重点:

https://leetcode-cn.com/problems/regular-expression-matching/solution/ji-yu-guan-fang-ti-jie-gen-xiang-xi-de-jiang-jie-b/

https://leetcode-cn.com/problems/wildcard-matching/


##  字符串匹配算法


 字符串匹配算法
1. 暴力法(brute force) - O(mn)
2. Rabin-Karp 算法
3. KMP 算法
课后了解:

Boyer-Moore 算法:
https://www.ruanyifeng.com/blog/2013/05/boyer-moore_string_search_algorithm.html 

Sunday 算法:
https://blog.csdn.net/u012505432/article/details/52210975


## 暴力法

```Java
public static int forceSearch(String txt, String pat) {
    int M = txt.length();
    int N = pat.length();
    for (int i = 0; i <= M - N; i++) {
        int j;
        for (j = 0; j < N; j++) {
            if (txt.charAt(i + j) != pat.charAt(j))
                break;
        }
        if (j == N) {
            return i;
        }
    // 更加聪明?
    // 1. 预先判断– hash(txt.substring(i, M)) == hash(pat)
    // 2. KMP
    }
    return -1;
}
```


## Rabin-Karp 算法

在朴素算法中，我们需要挨个比较所有字符，才知道目标字符串中是否包含子串。那么，是否有别的方法可以用来判断目标字符串是否包含子串呢?
答案是肯定的，确实存在一种更快的方法。为了避免挨个字符对目标字符串和子串进行比较，我们可以尝试一次性判断两者是否相等。
因此，我们需要一个好的哈希函数(hash function)。 通过哈希函数，我们可以算出子串的哈希值，然后将它和目标字符串中的子串的哈希值进行比较。 
这个新方法在速度上比暴力法有显著提升。

## Rabin-Karp 算法

Rabin-Karp 算法的思想:

1. 假设子串的长度为 M (pat)，目标字符串的长度为 N (txt)
2. 计算子串的 hash 值 
3. 计算目标字符串txt中每个长度为 M 的子串的 hash 值(共需要计算 N-M+1 次)
4. 比较 hash 值:如果 hash 值不同，字符串必然不匹配; 如果 hash 值相同， 还需要使用朴素算法再次判断

```Java
public final static int D = 256;
public final static int Q = 9997;

static int RabinKarpSerach(String txt, String pat) {
    int M = pat.length();
    int N = txt.length();
    int i, j;
    int patHash = 0, txtHash = 0;
    for (i = 0; i < M; i++) {
        patHash = (D * patHash + pat.charAt(i)) % Q;
        txtHash = (D * txtHash + txt.charAt(i)) % Q;
    }
    int highestPow = 1; // pow(256, M-1) 
    for (i = 0; i < M - 1; i++)
        highestPow = (highestPow * D) % Q;
    for (i = 0; i <= N - M; i++) { // 枚举起点 
        if (patHash == txtHash) {
            for (j = 0; j < M; j++) {
                if (txt.charAt(i + j) != pat.charAt(j))
                    break;
            }
            if (j == M) return i;
        }
        if (i < N - M) {
            txtHash = (D * (txtHash - txt.charAt(i) * highestPow) + txt.charAt(i + M)) % Q;
            if (txtHash < 0)
                txtHash += Q;
        }
    }
    return -1;
}
```

##  KMP 算法

KMP算法(Knuth-Morris-Pratt)的思想就是，当子串与目标字符串不匹配时，其实你已经知道了前面已经匹配成功那一部分的字符(包括子串与目标字符 串)。
以阮一峰的文章为例，当空格与 D 不匹配时，你其实 知道前面六个字符是 “ABCDAB”。KMP 算法的想法是，设法利用这个已知信息，不要把“搜索位置” 移回已经比较过的位置，
继续把它向后移，这样就提高了效率。

<https://www.bilibili.com/video/av11866460?from=search&seid=17425875345653862171>  
<http://www.ruanyifeng.com/blog/2013/05/Knuth–Morris–Pratt_algorithm.html>


## 参考链接

[Boyer-Moore 算法](http://www.ruanyifeng.com/blog/2013/05/boyer-moore_string_search_algorithm.html)
[Sunday 算法](https://blog.csdn.net/u012505432/article/details/52210975)
[KMP 字符串匹配算法视频](https://www.bilibili.com/video/av11866460?from=search&seid=17425875345653862171)
[字符串匹配的 KMP 算法](http://www.ruanyifeng.com/blog/2013/05/Knuth%E2%80%93Morris%E2%80%93Pratt_algorithm.html)
