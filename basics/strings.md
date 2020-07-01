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
for (int i = 0; i < x.length(); ++i) {
    char ch = x.charAt(i);
}
for (char ch : x.toCharArray()) {
    System.out.println(ch);
}
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


