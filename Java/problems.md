# Java 常见面试题

## Java 编程语言官方平台？

- Java Platform, Standard Edition (Java SE)
- Java Platform, Enterprise Edition (Java EE)
- Java Platform, Micro Edition (Java ME)
- JavaFX

## 对于Java平台的理解?

- Java语言特性，包括泛型、Lambda等语言特性；
- 基础类库，包括集合、IO/NIO、网络、并发、安全等基础类库。


Java 平台

  - Java 类库
    - 核心类库 IO/NI，网络， utils等
    - 安全类库
    - jdk.management
    - 海量的第三方类库
  - Java 虚拟机
    - 垃圾收集器
    - 运行时
    - 动态编译
    - 辅助功能： JFR 等
  - 工具
    - 辅助工具： jlink, jar, jdeps 
    - 编译器: javac, sjavac
    - 诊断工具： jmap, jstack, jconsole, jhsdb, jcmd




## Java是解释执行”，这句话正确吗？

我们开发的Java的源代码，首先通过Javac编译成为字节码（bytecode），然后，在运行时，通过 Java虚拟机（JVM）内嵌的解释器将字节码转换成为最终的机器码。但是常见的JVM，比如我们大多数情况使用的Oracle JDK提供的Hotspot JVM，都提供了JIT（Just-In-Time）编译器，也就是通常所说的动态编译器，JIT能够在运行时将热点代码编译成机器码，这种情况下部分热点代码就属于编译执行，而不是解释执行了。

Oracle Hotspot JVM内置了两个不同的JIT compiler:

- C1 client 模式 门限是1500次， 适用于对于启动速度敏感的应用
- C2 server模式的JVM，会进行上万次调用以收集足够的信息进行高效的编译

如JDK 8实际是解释和编译混合的一种模式，即所谓的混合模式（-Xmixed）