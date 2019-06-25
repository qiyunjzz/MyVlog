## java文件编程

---

[TOC]

### 1.java文件

java.io包几乎包含了所有操作输入，输出的类。

#### 读取控制台的输入

控制台输入由System.in完成，为了获得一个绑定到控制台的字符流，可以把System.in包装在BuferedReader对象中来创建一个字符流。tln()完成，这些方法都由类PrintStream定义，System.out使该类对象的一个引用。PrintStream继承与OutputStream类，并实现了write方法。

```java
System.out.write("str");
```

#### 读写文件

1. FileInputStream
   该流用于文件读取数据，它的对象可以用关键字new来创建。

   ```java
   InputStream fd = new FileInputStream("c:/java/hello");
   //或者
   File fd = new File("c:/java/hello");
   InputStream out = new InputStream(fd);
   ```

   InputStream方法

   1. close() throw IOExecption{} 关闭输入流，释放此流，抛出异常
   2. finalize()清除该文件的连接，不在引用输入流时，调用close。
   3. read() 读取指定字节的数据，返回整数，返回下一个字节数据，到文件结尾，返回-1.
   4. available(), 返回下一次对此输入流调用的方法可以不受阻塞的从此输入流读取的字节数。

2. FileOutputStream
   用来创建一个文件并向文件中写人数据。

   方法与InputStrema类似。

#### 文件和I/O

创建目录：File类
mkdir()
mkdirs() 创建文件夹

读取文件：FileReader类
list()

删除目录和文件：
java.io.File.delete()

### 2.java scanner类

java.util.Scanner类是java5的新特性。可以通过Scanner获取用户的输入。
用法：

```java
Scanner s = new Scanner(System.in);
if(s.hasNext()){
    String str = s.next();
    //或者
    String str1=  s.nextLine();
}
```

hasNext() 判断是否还有输入的数据。
next()和nextLine()的区别：
next（）：

1. 一定要读取到有效字符才可以结束。
2. 对输入有效字符之前遇到的空白字符，next()自动将它去除。
3. 只有输入有效字符，后面输入的空白字符才作为分隔符或者结束符。
4. next() 不能得到带有空格的字符串。

nextLine():

1. 以Enter为结束符，nextLine()返回输入回车之前的所有字符。
2. 可以获得空白。

**注意**：如果要输入int或float，Scanner也支持，输入之前最好用hasNextXxx()进行验证，再用nextXxx()读取。