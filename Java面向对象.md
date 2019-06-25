### java面向对象

---

[TOC]

#### 1.java 继承

java继承的意义在于代码复用。
java不支持多继承，只支持单继承，支持多重继承。

1. 继承的特性
   1. 子类拥有父类的非private 变量方法。
   2. 子类可以自由扩展，或重写父类的部分方法。
   3. 提高了类之间的耦合性(继承的缺点，耦合度高了，代码之间的联系就越紧密，代码独立性差)。

2. 继承关键字
   extends和implements,所有的类都是继承与java.lang.Object.

   extends:继承类。

   implemnets:继承接口。

3. super与this关键字

   super: 实现对父类成员的访问，用来引用当前对象的父类，所有构造方法的第一句是super()

   this:指向自己的引用

4. final
   final申明的类不能被继承，修饰的方法不能被重写。

### 2.重写(Override)与重载(Overload)

1. 重写
   1. 返回值和形参都不能改变，具体实现不同。不能抛出新的异常，或更宽泛的异常。
   2. 访问权限不能比父类的更低。
   3. 申明为static的方法不能被重写，但是可以被再次声明。
   4. 在同一包中，子类可以重写父类所有方法，除了private和final。
   5. 在不同包中，子类可以重写父类public,protected的非final方法。
   6. 构造方不能被重写。

2. 重载
   在同一个类中，方法名相同，参数不同。（相当与新的函数，但是名字要一样）

### 3.多态

同一个接口使用不同的实例而执行不同的操作。

1. 多态的优点：
   1. 消除类型之间的耦合关系
   2. 可替换性
   3. 可扩充性
   4. 接口性
   5. 灵活性
   6. 简化性

2. 多态的条件
   1. 继承
   2. 重写
   3. 父类引用指向子类对象（向上隐式转换）

### 4.多态的实现方法

1. 重写
2. 接口
3. 抽象类和抽象方法

### 5.抽象类

抽象类用abstract class来定义,没有足够的信息来描述一个类，叫抽象类，所有它不可被实例化。

```java
public abstract class Employee{
	private String name;
    public String getname(){
    	return name;
    }
    public abstract void computePay();
}
```

构造方法，类方法（static声明的方法）不能申明未抽象方法。

### 6.封装

优点：
1. 良好的封装能够减少耦合。

2. 类内部的结构可以自由修改。

3. 可以对成员变量进行更精确的控制。

4. 隐藏信息，实现细节。

### 7.java 接口

1. 接口的申明

```java
[可见度] interface 接口名称 [extends 其他接口的名字]{
	//申明变量
	//抽象方法
}
eg:
interface Animal {
   public void eat();
   public void travel();
}
```

接口是隐式抽象的，当声明一个接口的时候，不必使用abstract关键字。
接口中每一个方法也是隐式抽象的，声明时同样不需要abstract关键字。
接口中的方法都是公有的。

2. #### 接口的实现

```java
public class MammalInt implements Animal{
   public void eat(){
      System.out.println("Mammal eats");
   }
 
   public void travel(){
      System.out.println("Mammal travels");
   } 
 
   public int noOfLegs(){
      return 0;
   }
```

3. #### 接口的继承

   接口继承用extends。

   多继承格式： public interface Hockey extends Sports, Event

