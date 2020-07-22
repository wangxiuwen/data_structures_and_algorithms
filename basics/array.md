# 数组

>数组（Array）是一种线性表数据结构。它用一组连续的内存空间，来存储一组具有相同类型的数据
数组是线性表（Linear List）。顾名思义，线性表就是数据排成像一条线一样的结构。
每个线性表上的数据最多只有前和后两个方向。其实除了数组，链表、队列、栈等也是线性表结构
而与它相对立的概念是非线性表，比如二叉树、堆、图等。之所以叫非线性，是因为，在非线性表中，数据之间并不是简单的前后关系。

|  操作   | 复杂度  | 备注  |
|  ----  | ----  | ----  |
|  Access  | O(1) |   |
|  插入 insert | O(n) | 头O(n), 尾O(1), 平均O(n/2) 即 O(n) |
|  删除 delete | O(n) | 头O(n), 尾O(1), 平均O(n/2) 即 O(n) |


## JAVA 数组

>ArrayList 支持动态扩容，最好在创建ArrayList的时候事先指定数据大小
Java ArrayList无法存储基本类型，比如int、long，需要封装为Integer、Long类，而Autoboxing、Unboxing则有一定的性能消耗，所以如果特别关注性能，或者希望使用基本类型，就可以选用数组
如果数据大小事先已知，并且对数据的操作非常简单，用不到ArrayList提供的大部分方法，也可以直接使用数组
当要表示多维数组时，用数组往往会更加直观。比如Object[][] array；而用容器的话则需要这样定义：ArrayList<ArrayList > array


## 数组寻址

一维

```Java
a[k]_address = base_address + k * type_size;
```

二维

对于 `m * n` 的 二维数组， `a[i][j](i < m, j < n)` 的地址为:

```Java
a[i][j]_address = base_address + i * n * typesize + j * type_size
```

## Java ArrayList 拷贝


### 浅拷贝


```Java
List<Integer> l2 = new ArrayList<>(l1);
```

```Java
List<Integer> l2 = new ArrayList<>();
l2.addAll(l1);
```

### clone 拷贝

```Java
class CloneTest {
    static class Person implements Cloneable {

        int age;

        public Person(int age) {
            this.age = age; 
        }

        @Override
        protected Object clone() throws CloneNotSupportedException {
            return super.clone();
        }

    }

    public static void main(String[] args) {
        List<Person> l3 = new ArrayList<>();
        List<Person> l4 = new ArrayList<>();
        for (Person person : l3) {
            try {
                l4.add((Person) person.clone());
            } catch (CloneNotSupportedException e) {
                e.printStackTrace();
            }
        }
    }
}

```

### 深拷贝

```Java
public static <T> List<T> deepCopy(List<T> src) throws IOException, ClassNotFoundException {
    ByteArrayOutputStream byteOut = new ByteArrayOutputStream();
    ObjectOutputStream out = new ObjectOutputStream(byteOut);
    out.writeObject(src);

    ByteArrayInputStream byteIn = new ByteArrayInputStream(byteOut.toByteArray());
    ObjectInputStream in = new ObjectInputStream(byteIn);

    List<T> copy_list = (List<T>) in.readObject();
    return copy_list;
}
```

## 参考链接

[ArrayList 源码分析](http://developer.classpath.org/doc/java/util/ArrayList-source.html)  
[Linked List 的标准实现代码](https://www.geeksforgeeks.org/implementing-a-linked-list-in-java-using-class/)  
[Linked List 示例代码](http://www.cs.cmu.edu/~adamchik/15-121/lectures/Linked%20Lists/code/LinkedList.java)
[LinkedList源码分析](http://developer.classpath.org/doc/java/util/LinkedList-source.html)  
[ArrayList的深拷贝与浅拷贝](https://www.cnblogs.com/liusandao/p/12345208.html)