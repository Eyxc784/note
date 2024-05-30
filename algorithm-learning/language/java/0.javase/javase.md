# introduction

## java技术体系

| JavaSE(Java Standard Edition)标准版   | JavaSE是基础，主要学习的是Java语法、面向对象、集合、IO、多线程等基础 |
| ------------------------------------- | ------------------------------------------------------------ |
| JavaEE(Java Enterprise Edition)企业版 | JavaEE，Java最大的用处就是做WEB层的应用，而JavaEE，也就是企业版的应用，生态体系极为庞大，主流的就是Spring全家桶，要学的框架也是很多包括MyBatis、SpringMVC、SpringBoot等，自学的时候先学习Servlet那套，然后是SSM，最后SpringBoot。学会了，你也可以自己做自己的网站。（目前不用了解太多，学了就知道是什么了） |
| Java ME(Java Micro Edition)微型版     | 支持Java程序运行在移动终端平台(如手机、PDA等)，对Java API有所精简。自从android系统出来后，Java ME就很少用了。这个不学。 |

## 面向对象编程

**Java是一种纯面向对象编程的语言**

目前程序有两类：

第一类是程序员通过编写逻辑过程，让程序按照编写的逻辑来执行

第二类是目前的机器学习，深度学习，神经网络这类通过训练数据调参，程序根据模型进行预测



编写执行逻辑又有两类：面向过程和面向对象。

面向过程就是，完成一个任务，编写每一步的执行逻辑。

面向对象就是，创建多个对象，每一个对象负责完成一个具体的功能，为了完成一个任务，将每一步交给每一个对象去实现。

在编写大型工程的时候，面向对象是优于面向过程的。因为面向对象编程可以减少代码的重复，同时将不同的功能交由不同的对象去实现，这样通过不同的调用方式，可以实现不同的任务。而且逻辑比面向过程能清晰。



## Java开发工具

开发工具：开发人员用到的工具。

文本编辑器：vscode

IDE: IDEA



~~我觉得作为一个计算机初学者，在学一门编程语言的时候，应该先用文本编辑器编写程序，等到熟练了再学使用IDE，这样既能加深对程序的执行过程有了解，又能知道什么是IDE，等IDE学会了，就去玩vscode，学会DIY自己的IDE，一方面能锻炼程序员环境的配置，了解更多原理，又能搭配适合自己的IDE。~~

我觉得作为一个计算机初学者，没必要知道什么是编辑器、IDE这种概念，该用哪款软件就用哪款软件。等用的熟练了自然就知道了。初学者没必要纠结这些。

## JDK介绍

首先介绍Java跨平台的机理：

**JVM：Java Virtual Machine(Java虚拟机)**。在真实的计算机中模拟出一台计算机。虚拟机有自己完善的硬体架构(通过编写代码模拟出来的)，如处理器、堆栈、寄存器、指令系统等。

实现Java程序的跨平台性

<img src=javase.assets/1704706422655.png width=40% padding=20% align=left>

**JDK：Java Development Kit**。(Java开发工具包)

JDK = JRE + java开发工具集

**JRE：Java Runtime Environment**.（Java运行时环境）

JRE = JVM + Java的核心类库 

平时也会遇到SDK，自行网页搜索。

首先讲什么是JRE，**JRE是指Java程序运行时所需要的环境，也就是Java程序要运行的话不可缺少的东西**：JVM和核心类库。

对于用户来说，用户只需要.class文件和JRE就可以运行程序了。

对于开发者来说，开发者需要先编写Java程序，然后使用Java开发工具集里的工具，如javac.exe(编译器)将.java程序编译成.class文件、java.exe（解释器）、javadoc（网页文档生成器）等。因此，对于开发者来说，需要完整的JDK

![1711613618824](javase.assets/1711613618824.png)

## 环境变量的配置

python介绍过，这里不再介绍。

## Java代码规范

java开发涉及各方面的知识，现有的开发手册如阿里云、华为的java开发手册覆盖了各方面的开发规范，我们目前只是java的初学者，并不会要求一上来就去读Java开发规范手册。目前我们只了解一些java代码规范，为我们后续的学习打下良好的基础。

1. 类、方法的注释使用文档注释
2. 使用tab键和shift+tab键实现缩进和取消缩进，不要用空格。
3. 运算符和=两边留空格
4. 源文件用utf-8编码
5. 一行代码不要写太长，不便于阅读
6. 左大括号换行或不换行均可，要选一种，别混用！

## java程序从编写到运行

创建Hello.java的文件

编写代码如下：(注意:**文件名 `Hello`需要与类名 `Hello` 保持一致，注意大小写有区别**)

```java
public class Hello{
	public static void main(String[] args)
	{
		System.out.println("Hello,world");
	}
}
```

对于上述java代码，学过面向对象才知道每一部分表示的含义，对于新人，记住这个框架，在main函数里编程即可。

在地址栏中输入cmd并回车，即可打开终端窗口。输入 `javac hello.java`进行编译生成`hello.class`

再输入 `java hello`就会执行这个class文件

> 注意编译和运行时的区别，在编译的时候使用的是javac.exe这个编译工具，处理的文件是带有后缀".java"的，而在运行的时候，使用的工具是java.exe,处理的文件是不带有后缀".class"的
>

**每一次修改代码，都要经历保存，编译，运行三个过程。**



Java源文件以.java为扩展名。源文件的基本组成单位是类(class)

一个源文件最多只能有一个public类，如果源文件中有一个public类，则文件名必须与该public类的类名保持一致。

一个源文件如下：

```java
// hello.java
public class hello{
	public static void main(String[] args)
	{
		System.out.println("hello,world");
	}
}

class Dog
{
	public static void main(String[] args)
	{
		System.out.println("hello,dog");
	}
}

class Tiger
{
	public static void main(String[] args)
	{
		System.out.println("hello,tiger");
	}
}
```

在cmd经过编译 `javac hello.java`之后生成三个文件 `hello.class`、`Dog.class`、 `Tiger.class`

分别运行这三个`.class`文件，会分别执行这三个类的main函数。

由上可知：

1. 源文件中的每一个类经过编译都会生成对应的class文件

2. main函数可以在多个类中实现，分别执行对应类的.class文件可以执行该类中的main函数



# 基本语法

### 注释(comment)

```java
//单行注释

/*
多~
行~
注~
释~
*/

```



**文档注释**

文档注释可以被JDK提供的工具javadoc解析，生成网页格式的说明文档，也就是API文档。

[Java 文档注释全攻略，建议收藏！ - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/619502562#:~:text=二、文档注释格式总结 1 所有的 Java 文档注释都以 %2F** 开头， *%2F,每个 Java 文档注释都要和其后对应的类%2F方法%2F字段%2F包保持同样的缩进 4 Java 文档注释的内容，支持采用 HTML 语法规则书写，同时也支持一些额外的辅助标签)

[0024_韩顺平Java_文档注释_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1fh411y7R8?p=25&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

了解即可，用不着自己写文档注释

### API文档

- API （Application Programming Interface，应用程序编程接口）
- **Java语言提供了大量的基础类**，因此 Oracle 也为这些基础类提供了相应的说明文档，**用于告诉开发者如何使用这些类，以及这些类里包含的方法。**

  在线看：https://docs.oracle.com/en/java/javase/17/docs/api/index.html

### 关键字(keyword)

- 定义：**被Java语言赋予了特殊含义，用做专门用途的字符串（或单词）**

![1707380816771](javase.assets/1707380816771.png)

> 说明：
>
> 1. 关键字一共`50个`，其中`const`和`goto`是`保留字`(reserved word)。
> 2. `true`，`false`，`null`不在其中，它们看起来像关键字，其实是`字面值(iterals)`，表示特殊的布尔值和空值。

strictfp了解一下即可，以后不会用到。。



### 标识符(identifier)

Java中开发人员起的变量名、方法名、类名，称为标识符。

**标识符的命名规则**（必须遵守的`硬性规定`）：

- 由26个英文字母大小写，0-9 ，_或 $ 组成  
- 数字不可以开头。
- 不可以使用关键字和保留字，但能包含关键字和保留字。
- Java中严格区分大小写，长度无限制。

**标识符的命名规范**（建议遵守的`软性要求`，否则工作时容易被鄙视）:

> 包名：多单词组成时所有字母都小写
> 例如：java.lang、com.atguigu.bean
>
> 类名、接口名：多单词组成时，所有单词的首字母大写：XxxYyyZzz
> 例如：HelloWorld，String，System等
>
> 变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写：xxxYyyZzz
> 例如：age,bookName,getName
>
> 常量名：所有字母都大写。多单词时每个单词用下划线连接：XXX_YYY_ZZZ
> 例如：MAX_VALUE,PI,DEFAULT_CAPACITY

注意：在起名字时，为了提高阅读性，要尽量有意义，“见名知意”。更多细节详见《代码整洁之道_关于标识符.txt》《阿里巴巴Java开发手册-1.7.1-黄山版》



### 变量(variable)

- 变量的概念：
  - 内存中的一个存储区域
  - 变量的构成包含三个要素：`数据类型`、`变量名`、`存储的值`
  - Java中变量声明的格式：`数据类型 变量名 = 字面值(literals)或地址;`
- 使用变量注意：
  - Java中每个变量必须先声明，后使用。
  - 使用变量名来获取这块区域的数据。
  - 变量的作用域：其定义所在的一对{ }内。变量只有在其`作用域`内才有效。
  - 同一个作用域内，不能定义重名的变量。

java不支持外层块定义一个变量，在内层块再定义一个同名变量

> With java, you cannot make a local variable with the same name, even though the data types are different.

```java
public static void main(String[] args)
{
    int i = 1;
    for(int i = 0;;)    //在main中定义了变量i，再在内层块定义会报错。
    {
        
    }
}
```

### 数据类型

<img src=javase.assets/1707381266490.png width=80% align=left>

什么是引用数据类型？

引用数据类型的变量存放的是地址。而基本数据类型的变量存放的是值。



java与c不同，java的数据类型有固定的字节，不受具体操作系统的影响，而c++各数据类型的字节大小是受到具体cpu的机器字长影响。这一特性保证了java可移植性。

| 数据类型 | 存储方式     | 字节大小 | 取值范围      | 默认值   |
| -------- | ------------ | -------- | ------------- | -------- |
| byte     | 有符号、补码 | 1        | 自己算        | 0        |
| short    | 有符号、补码 | 2        |               | 0        |
| int      | 有符号、补码 | 4        |               | 0        |
| long     | 有符号、补码 | 8        |               | 0L       |
| float    | IEEE754      | 4        |               | 0.0f     |
| double   | IEEE754      | 8        |               | 0.0d     |
| boolean  |              | ~        | true or false | false    |
| char     |              | 2        |               | '\u0000' |

> boolean类型不能用0、非0代替flase、true

定义基本数据类型的变量的时候，系统会根据其数据类型给变量分配对应字节大小的空间。（局部变量是没有默认值的）

引用数据类型的默认值是null

### 字面值(literals)

字面值也有数据类型！

在默认值那一列可以看到0有四种表示形式，分别是：0，0L，0.0f，0.0d

Java中默认将整数字面值视为 `int` 类型。在整数字面值后面添加 `L` 或 `l` 来表示`long` 类型

Java中默认将浮点数字面值视为`double`类型。在浮点数字面值后面添加`f`或`F`表示`float`类型，在浮点数字面值后面添加`d`或`D`表示`double`类型

浮点型字面值有两种表示形式：

- 十进制数形式。如：5.12       512.0        .512   (必须有小数点）
- 科学计数法形式。如：5.12e2      512E2     100E-2

```java
double num1 = 0.314;
double num1 = .314; //等价于0.314
double num2 = 3.14e3; // 3.14e3 = 3.14*10^3
double num3 = 3.14E3;  //e、E是一样的
System.out.println(num1);   // 0.314
System.out.println(num2);  //  3140.0
```

**浮点数陷阱**

```java
double num1 = 2.7;
double num2 = 8.1 / 3;    // 正常计算应该是2.7
System.out.println(num1);  // 2.7
System.out.println(num2);  // 2.6999999999999997
```

出现这种情况，需要学习浮点数的乘除，必须要学会！（考研考到了）

综上，不要用浮点数相等作为判断条件：

```java
if(num1 == num2)
{
    System.out.println("2.7 = 8.1 / 3");
}
else
{
    System.out.println("2.7 != 8.1 / 3");
}
```

正确的做法是：两个数相减的绝对值小于1e-6或1e-15

如果是float类型的，要小于1e-6

如果是double类型的，要小于1e-15

为什么是这样，具体原因与浮点数的存储方式有关！

- 并不是所有的小数都能可以精确的用二进制浮点数表示。二进制浮点数不能精确的表示0.1、0.01、0.001这样10的负次幂。（这个也是跟浮点数的存储方式有关）
- 浮点类型float、double的数据不适合在`不容许舍入误差`的金融计算领域。如果需要`精确`数字计算或保留指定位数的精度，需要使用`BigDecimal类`,可以实现任意精度的数据的运算。

**在变量定义的时候，整型变量常用int，浮点数变量常用double**

> 为什么Java中0.1 + 0.2结果不是0.3？（字*跳动）
>
> 在代码中测试0.1 + 0.2，你会惊讶的发现，结果不是0.3，而是0.3000……4。这是为什么？
>
> 几乎所有现代的编程语言都会遇到上述问题，包括 JavaScript、Ruby、Python、Swift 和 Go 等。引发这个问题的原因是，它们都采用了`IEEE 754标准`。

学计组的时候再算算！！！

### 类型转换(看底层)

1. boolean类型不参与转换

2. 自动转换

   编译器自动完成数据类型转换

   1. 将低级字面值赋给高级变量时

      ```java
byte myByte = 0;
      // 字面值0是int类型，字节大小为4，而变量myByte是byte类型，字节大小为1，当您将一个整数赋值给一个byte类型的变量时，如果该整数在 byte 类型的取值范围内（即 -128 到 127），则赋值是有效的，这个过程进行了自动类型转换。如果整数超出了byte类型的取值范围，那么编译器将报错
   int n1 = 0;
      byte n2 = n1; 
   //但是将一个int类型变量赋值给一个byte类型的变量时，编译器将报错。不管超没超byte类型的取值范围。
      ```
      
   2. 进行运算时
   
      不同数据类型的数字进行运算时，需要先转换成同样的数据类型才能计算,当存储范围小的数据类型与存储范围大的数据类型变量一起混合运算时，会按照其中最大的类型运算。
   
      ```java
      int i = 1;
   byte b = 1;
   double d = 1.0;
   
      double sum = i + b + d;//混合运算，升级为double
      ```
   ```java
   //当byte,short,char数据类型的变量进行算术运算时，按照int类型处理。
   byte b1 = 1;
   byte b2 = 2;
   byte b3 = b1 + b2;//编译报错，b1 + b2自动升级为int
   
   char c1 = '0';
   char c2 = 'A';
   int i = c1 + c2;//至少需要使用int类型来接收
   System.out.println(c1 + c2);//113 
   ```
   
   ![1706097336567](javase.assets/1706097336567.png)
   
   虚线表示可能丢失精度
   
3. 强制转换

   程序员强制要求进行数据类型转换,可能会有精度的损失，一般不建议这样使用。


（1）当把存储范围大的值（常量值、变量的值、表达式计算的结果值）强制转换为存储范围小的变量时，可能会`损失精度`或`溢出`。

```java
int i = (int)3.14;//损失精度

double d = 1.2;
int num = (int)d;//损失精度

int i = 200;
byte b = (byte)i;//溢出
```

（2）当某个值想要提升数据类型时，也可以使用强制类型转换。这种情况的强制类型转换是`没有风险`的，通常省略。

```java
int i = 1;
int j = 2;
double bigger = (double)(i/j);
```

```java
long l1 = 123L;
long l2 = 123;// int类型的123自动类型提升为long类型,这直接看底层就好了呀。

//long l3 = 123123123123; //报错，因为123123123123超出了int的范围。
long l4 = 123123123123L;


//float f1 = 12.3; //报错，因为12.3看做是double，不能自动转换为float类型
float f2 = 12.3F;
float f3 = (float)12.3;
```



### 字符(char)

- Java中的所有字符都使用Unicode编码

- 字符型字面值的三种表现形式：

  - **形式1：**使用单引号(' ')括起来的`单个字符`。

    例如：char c1 = 'a';   char c2 = '中'; char c3 =  '9';

  - **形式2：**直接使用 `Unicode值`来表示字符型常量：‘`\uXXXX`’。其中，XXXX代表一个十六进制整数。

    例如：\u0023 表示 '#'。

  - **形式3：**Java中还允许使用`转义字符‘\’`来将其后的字符转变为特殊字符型常量。

    例如：char c3 = '\n';  // '\n'表示换行符

  | 转义字符 |  说明  | Unicode表示方式 |
  | :------: | :----: | :-------------: |
  |   `\n`   | 换行符 |     \u000a      |
  |   `\t`   | 制表符 |     \u0009      |
  |   `\"`   | 双引号 |     \u0022      |
  |   `\'`   | 单引号 |     \u0027      |
  |   `\\`   | 反斜线 |     \u005c      |
  |   `\b`   | 退格符 |     \u0008      |
  |   `\r`   | 回车符 |     \u000d      |

- char类型是可以进行运算的。因为它都对应有Unicode码，可以看做是一个数值。

char类型计算的时候，是Unicode码参与计算

```java
char c = '\r',d = '\n';
System.out.print(c+d);  // '\r'=000d=13,'\n'=000a=10
-----------
23    
```

### 编码

字符集：字符与(十进制)码点的映射。

编码方案：二进制码点与真实底层存储的映射。



[05、IO流（一）：前置知识-字符集、UTF-8、GBK、ASCII、乱码问题、编码和解码等_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Cv411372m?p=156&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

### 转义字符

在Java中，反斜杠（\）是一个特殊的字符，被称为转义字符，它的作用是用来转义后面一个字符，用于表示特殊含义，接下来介绍几个

```java
//Hello.java
public class Hello
{
    public static void main(String[] args)
    {
        System.out.println("hello,world\n你好，世界");
    }
}
------
hello,world
你好，世界
```

```java
//Hello.java
class number
{
    public static void main(String[] args)
    {
        System.out.println("1234567\t12345678\t123456789\t1")
    }
}
----------
1234567 12345678        123456789       1

//第一个\t前面有7位字符，不满8位，补空格至8位
//第二个\t前面有8位字符，不满16位，补空格至16位
//第三个\t前面有9位字符，不满16位，补空格至16位
```

综上，制表符\t前面的字符数不足或等于8的倍数时，补空格至8的倍数。

```java
//Hello.java
class Enter
{
    public static void main(String[] args)
    {
        System.out.println("人人得而诛之\r非也");
    }
}
-----------
非也得而诛之    
```

在java中，用双引号括起来的部分表示字符串，如果我们想在字符串内使用双引号，如：

他们说："人生不得意之事十之八九"。

```java
class Escape
{
    public static void main(String[] args)
    {
        System.out.println("他们说：\"人生不得意之事十之八九\"。")
        //要在需要识别成字符的引号前加\
    }
}
```

因为双引号`"`会被编译器识别为字符串的标志，而我们希望双引号作为字符串的一部分，即我们希望双引号被识别成一个字符，因此我们可以在双引号前加反斜杠，这样编译器就能将其识别为字符。

综上可知,如果我们想在字符串中使用 `\`,会被编译器直接识别为转义字符，而转义字符是与其后的字符结合会产生效果的。因此我们需要在 `\`前加 `\`，这样就能被识别成字符了。

### 布尔类型(boolean)

- **boolean类型数据只有两个值：true、false。**
  - 不可以使用0或非 0 的整数替代false和true，这点和C语言不同。

> 经验之谈：
>
> Less is More！建议不要这样写：if ( isFlag = = true )，只有新手才如此。关键也很容易写错成if(isFlag = true)，这样就变成赋值isFlag为true而不是判断！`老鸟的写法`是if (isFlag)或者if ( !isFlag)。

### 字符串类型(String)

- String不是基本数据类型，属于引用数据类型

- 使用一对`""`来表示一个字符串，内部可以包含0个、1个或多个字符。

  ```
  String s = "hello,world!";
  ```

1、任意基本数据类型的数据与String类型只能进行连接“+”运算，且结果一定也是String类型

```java
System.out.println("" + 1 + 2);//12

int num = 10;
boolean b1 = true;
String s1 = "abc";

String s2 = s1 + num + b1;
System.out.println(s2);//abc10true

//String s3 = num + b1 + s1;//编译不通过，因为int类型不能与boolean运算
String s4 = num + (b1 + s1);//编译通过
```

2、String类型不能通过强制类型转换，转为其他的类型

```java
String str = "123";
int num = (int)str;//错误的

int num = Integer.parseInt(str);//正确的，后面才能讲到，借助包装类的方法才能转
```

与c不同的是，Java的String类不支持方括号运算符

```java
String s = "Hello,world!";
System.out.println(s[0]);     //在java中，用运算符[]来获取索引对应的元素，是错误的。但char[]数组依然支持
System.out.println(s.charAt(0));  //正确的做法！！！
```

String类提供charAt()方法来获取索引对应的元素。

### 运算符(Operator)

运算符的分类：

- 按照`功能`分为：算术运算符、赋值运算符、比较(或关系)运算符、逻辑运算符、位运算符、条件运算符、Lambda运算符

```java
public class Test {
    public static void main(String args[]) {
        int x = -5;
        int y = -12;
        System.out.println(y % x);
    }
}
```

取模运算（“Modulus Operation”）和取余运算（“Remainder Operation ”）两个概念有重叠的部分但又不完全一致。主要的区别在于对负整数进行除法运算时操作不同。取模主要是用于计算机术语中。取余则更多是数学概念。 

> 取余的结果是与被除数的符号保持一致；
> 取模的结果是与除数的符号保持一致。

另外各个环境下`%`运算符的含义不同，比如C/C++，Java 为取余，而Python则为取模。

在java中，%为取余操作，Math.floorMod为取模操作



|           分类            |                        运算符                        |
| :-----------------------: | :--------------------------------------------------: |
|     算术运算符（7个）     |                +、-、*、/、%、++、--                 |
|    赋值运算符（12个）     | =、+=、-=、*=、/=、%=、>>=、<<=、>>>=、&=、\|=、^=等 |
| 比较(或关系)运算符（6个） |                 >、>=、<、<=、==、!=                 |
|     逻辑运算符（6个）     |                &、\|、^、!、&&、\|\|                 |
|      位运算符（7个）      |               &、\|、^、~、<<、>>、>>>               |
|     条件运算符（1个）     |               (条件表达式)?结果1:结果2               |
|    Lambda运算符（1个）    |                          ->                          |

- 按照`操作数个数`分为：一元运算符（单目运算符）、二元运算符（双目运算符）、三元运算符 （三目运算符）

|           分类            |                  运算符                  |
| :-----------------------: | :--------------------------------------: |
| 一元运算符（单目运算符）  |    正号（+）、负号（-）、++、--、!、~    |
| 二元运算符（双目运算符）  | 除了一元和三元运算符剩下的都是二元运算符 |
| 三元运算符 （三目运算符） |         (条件表达式)?结果1:结果2         |

> 面试题：三元操作符如果遇到可以转换为数字的类型，会做自动类型提升。 (底层不太了解)
>
> ```java
> public static void main(String[] args) {
>     Object o1 = true ? new Integer(1) : new Double(2.0);
>     Object o2;
>     if (true) {
>     o2 = new Integer(1);
>     } else {
>         o2 = new Double(2.0);
>     }
>     System.out.print(o1);      // 1.0
>     System.out.print(" ");         
>     System.out.print(o2);      // 1
> }
> ```
>
> 

**自增运算符**

（底层不太了解）

以下代码执行的结果显示是多少（）？

![img](javase.assets/5994168_1502783973150_A3AECBB367EA2A16CE5EC419126BC346.png)

答案：num * count = 0

`count = count++;`

执行过程：先执行`count++`

count++是先赋值后加=>   temp = count  ， count = count + 1； 即先把count的值放到一个临时变量中，然后执行count = count + 1。即count = 1

接着执行赋值运算符，即将临时变量temp的值赋给count。即count = 0；

因此， `count = count++;`执行完后count的值不变。

**赋值运算符**

| 赋值运算符 |                           符号解释                           |
| :--------: | :----------------------------------------------------------: |
|    `+=`    | 将符号`左边的值`和`右边的值`进行`相加`操作，最后将结果`赋值给左边的变量` |
|    `-=`    | 将符号`左边的值`和`右边的值`进行`相减`操作，最后将结果`赋值给左边的变量` |
|    `*=`    | 将符号`左边的值`和`右边的值`进行`相乘`操作，最后将结果`赋值给左边的变量` |
|    `/=`    | 将符号`左边的值`和`右边的值`进行`相除`操作，最后将结果`赋值给左边的变量` |
|    `%=`    | 将符号`左边的值`和`右边的值`进行`取余`操作，最后将结果`赋值给左边的变量` |

```java
short s1=1; 
s1=s1+1;  //有什么错？  =右边是int类型。需要强转

short s1=1;
s1+=1; //有什么错?   没错
```

**位运算符**

```java
A = 0011 1100
B = 0000 1101
-----------------
A & B = 0000 1100
A | B = 0011 1101
A ^ B = 0011 0001
~A= 1100 0011
```

| 操作符 | 描述     |
| ------ | -------- |
| &      | 按位与   |
| I      | 按位或   |
| ~      | 按位非   |
| ^      | 按位异或 |
| <<     | 算术左移 |
| \>>    | 算术右移 |
| \>>>   | 逻辑右移 |

```java
int a = -15,b = -15;
a = a >> 1;  
b = b >>> 1;
System.out.println(a);   
System.out.println(b);
---------
    
-8
2147483640    
```

可知，符号位是什么， `>>` 右移补什么。  `>>>`右移补0

**逻辑运算符**

| &&    | 当且仅当两个操作数都为真，条件才为真。                       |
| ----- | ------------------------------------------------------------ |
| \| \| | 如果任何两个操作数任何一个为真，条件为真。                   |
| ！    | 称为逻辑非运算符。用来反转操作数的逻辑状态。如果条件为true，则逻辑非运算符将得到false。 |

java逻辑运算符支持短路

```java
public class Test {
    private static int j = 0;
 
    private static Boolean methodB(int k) {
        j += k;
        return true;
    }
 
    public static void methodA(int i) {
        boolean b;
        b = i < 10 | methodB(4);
        b = i < 10 || methodB(8);
 
    }
 
    public static void main(String args[]) {
        methodA(0);
        System.out.println(j);
    }
}
```

输出结果j为4.因为     `||` 前边是true，根据短路原则，methodB(8)不再执行。



**条件运算符**

```java
int a , b;
a = 10;
// 如果 a 等于 1 成立，则返回 20，否则 30
b = (a == 1) ? 20 : 30;
System.out.println( "Value of b is : " +  b );
```



**运算符优先级**

运算符有不同的优先级，所谓优先级就是在表达式运算中的运算符顺序。

上一行中的运算符总是优先于下一行的。

| 优先级 |    运算符说明    |             Java运算符             |
| ------ | :--------------: | :--------------------------------: |
| 1      |       括号       |          `()`、`[]`、`{}`          |
| 2      |      正负号      |              `+`、`-`              |
| 3      |    单元运算符    |       `++`、`--`、`~`、`！`        |
| 4      | 乘法、除法、求余 |           `*`、`/`、`%`            |
| 5      |    加法、减法    |              `+`、`-`              |
| 6      |    移位运算符    |         `<<`、`>>`、`>>>`          |
| 7      |    关系运算符    | `<`、`<=`、`>=`、`>`、`instanceof` |
| 8      |    等价运算符    |             `==`、`!=`             |
| 9      |      按位与      |                `&`                 |
| 10     |     按位异或     |                `^`                 |
| 11     |      按位或      |                `|`                 |
| 12     |      条件与      |                `&&`                |
| 13     |      条件或      |                `||`                |
| 14     |    三元运算符    |               `? :`                |
| 15     |    赋值运算符    | `=`、`+=`、`-=`、`*=`、`/=`、`%=`  |
| 16     |   位赋值运算符   |  `&=`、`|=`、`<<=`、`>>=`、`>>>=`  |

> 开发建议：
>
> 1. 不要过多的依赖运算的优先级来控制表达式的执行顺序，这样可读性太差，尽量`使用()来控制`表达式的执行顺序。
> 2. 不要把一个表达式写得过于复杂，如果一个表达式过于复杂，则把它`分成几步`来完成。例如：
>    ​ (num1 + num2) * 2 > num3 && num2 > num3 ? num3 : num1 + num2;



别想着优先级不用记，多加括号就行。一旦遇到面试就直接没分了，有了工作后忘了就行。



### 条件语句

```java
if(布尔表达式)
{
   //如果布尔表达式为true将执行的语句
}
```

```java
if(布尔表达式){
   //如果布尔表达式的值为true
}else{
   //如果布尔表达式的值为false
}
```

```java
if(布尔表达式 1){
   //如果布尔表达式 1的值为true执行代码
}else if(布尔表达式 2){
   //如果布尔表达式 2的值为true执行代码
}else if(布尔表达式 3){
   //如果布尔表达式 3的值为true执行代码
}else {
   //如果以上布尔表达式都不为true执行代码
}
```

```java
if(布尔表达式 1){
   ////如果布尔表达式 1的值为true执行代码
   if(布尔表达式 2){
      ////如果布尔表达式 2的值为true执行代码
   }
}
```

### 循环语句

```java
while( 布尔表达式 ) {
  //循环内容
}
```

对于 while 语句而言，如果不满足条件，则不能进入循环。但有时候我们需要即使不满足条件，也至少执行一次。

do…while 循环和 while 循环相似，不同的是，do…while 循环至少会执行一次。

```java
do {
       //代码语句
}while(布尔表达式);
```

```java
for(初始化; 布尔表达式; 更新) {
    //代码语句
}
```

```java
for(声明语句 : 表达式)
{
   //代码句子
}
```

```java
public class Test {
   public static void main(String[] args){
      int [] numbers = {10, 20, 30, 40, 50};
 
      for(int x : numbers ){
         System.out.print( x );
         System.out.print(",");
      }
      System.out.print("\n");
      String [] names ={"James", "Larry", "Tom", "Lacy"};
      for( String name : names ) {
         System.out.print( name );
         System.out.print(",");
      }
   }
}
```

### break&continue

### 方法&return

方法的定义：

```java
修饰符 返回值类型 方法名(形参列表){
    //方法体
    return 返回值;
}    
```

修饰符在学习封装的时候会学。

方法的作用：

将代码进行封装，以便可以重复的被调用，即降低代码的重复性。同时将代码封装可以使整体代码的逻辑更清晰。



参数传递机制

Java里方法的参数传递方式只有一种： 值传递 。 即将实际参数值的副本（复制品）传入方法内，而参数本身不受影响。
形参是基本数据类型：将实参基本数据类型变量的“数据值”传递给形参
形参是引用数据类型：将实参引用数据类型变量的“地址值”传递给形参

以下Java程序运行的结果是

```java
public class Tester{
public static void main(String[] args){
   Integer var1=new Integer(1);
   Integer var2=var1;
   doSomething(var2);
   System.out.print(var1.intValue());   // 1
   System.out.print(var1==var2);        // true
}
public static void doSomething(Integer integer){
    integer=new Integer(2);
    }
}
```

<img src=javase.assets/579609_1469695671774_8A5F006FFD4CE801C8E888EC3BC68361.png width=40% align=left>

### 递归

学习递归能帮助我们理解，在底层，方法在调用后是存放在栈区里的。

### switch

```java
switch(expression){
    case value :
       //语句
       [break;]
    case value :
       //语句
       [break;]
    //你可以有任意数量的case语句
    [default : 语句]
}
```

- switch 语句中的表达式的类型可以是： byte、short、int 、char或枚举类型。从 Java SE 7 开始，switch 支持字符串 String 类型了；value必须为字面量。

  

- **计算switch后表达式expression的值，并逐个与case后常量表达式value的值相比较，当表达式expression的值与某个常量表达式value的值相等时，即执行其后的语句，直到遇到break语句为止。如表达式的值与所有case后的常量表达式均不相同时，则执行default后的语句。**(深刻理解)

- switch 语句可以包含一个 default 分支，case和default只起标号的作用，顺序可以颠倒。default 在没有value和expression相等的时候执行

  ```java
  public class Test {
     public static void main(String args[]){
        int i = 1;
        switch(i){
           case 0:
              System.out.println("0");
           case 1:
              System.out.println("1");
           case 2:
              System.out.println("2");
           default:
              System.out.println("default");
        }
     }
  }
  -------
  1
  2
  default    
  ```



### 输入输出语句

输出语句

```java
public static void main(String[] ags){           
    System.out.println("1");   
    System.out.println();
    System.out.println("2");   //自带换行
    System.out.print("3");     //不带换行
    System.out.print("4");
}
-------------
1

2    
34    
```

输入语句

```java
import java.util.Scanner;

Scanner scan = new Scanner(System.in);   //实例化类Scanner
String str = scan.nextline();        //调用scan中的方法nextline(),从键盘获取一串字符串并返回
```

### 一维数组

- 创建数组会在内存中开辟一整块`连续的空间`。占据的空间的大小，取决于数组的长度和数组中元素的类型。
- 数组，一旦初始化完成，其长度就是确定的。数组的`长度一旦确定，就不能修改`。
- 我们可以直接通过下标(或索引)的方式调用指定位置的元素
- 数组名是这块连续空间的首地址。

```java
// 1.声明
int[] arr;   
int arr[];  
/* 注意:建议使用int[] arr;声明数组变量。int arr[];来自C/C++，在Java中采用是为了让C/C++程序员能够快速
上手Java语言*/
// 2.分配空间
arr = new int[arraySize];   
/*创建一个大小为arraySize，元素类型为int的数组，并将首地址赋给arr，arraySize可以是字面值，也可以是变量或常量*/
// 3.声明并分配空间
int[] arr = new int[arraySize];
```

> 动态初始化和静态初始化的区别？
>
> 举个例子
>
> 让用户输入一个数字n，表示接下来用户将输入n个数，并用数组存储起来。在这种预先不知道数组大小的情况下，只能用动态创建数组的方法。

动态初始化

```java
int n = 5;
int[] a = new int[n];
System.out.println(a.length);   // 5    数组的长度用length属性
```

静态初始化

```java
int[] arr = new int[5];  //默认值
int[] arr = new int[]{1,2,3,4,5};
int[] arr = {1,2,3,4,5};
```

索引用中括号[]

> 为什么数组要从0开始编号，而不是1
>
> 数组的索引，表示了数组元素距离首地址的偏离量。因为第1个元素的地址与首地址相同，所以偏移量就是0。所以从0开始。

```java
char[] letters = new char[5];
System.out.println("letters数组的长度：" + letters.length);
if(letters[0] == '\u0000')
{
    System.out.println("6");
}
if(letters[0] == 0)
{
    System.out.print("6");
}
-----
66    
```

**根据上面这个例子可知，char类型的默认值是'\u0000',也是int类型的字面量0**，因为，`\u`是转义字符，表示后面的数字是十六进制。十六进制的0000就是十进制的0啊。

打印地址

```java
int[] arr = {1,2,3,4,5};
System.out.println(arr);//[I@6d03e736
```

> 以[I@6d03e736为例：
> [ ：表示现在打印的是一个数组。
> I：表示现在打印的数组是int类型的。
> @：仅仅是一个间隔符号而已。
> 6d03e736：就是数组在内存中真正的地址值。（十六进制的）
> 但是，我们习惯性会把[I@6d03e736这个整体称之为数组的地址值

以上提到的是定长数组，可变长数组在集合框架中学。

### 二维数组

```java
//推荐
int[][] arr;

//不推荐
int  arr[][];
//不推荐
int[]  arr[];
```

法一：

```java
int[][] arr = {{1,2,3},{4,5,6},{7,8,9,10}};
```

法二：

```java
int[][] arr = new int[][]{{3,8,2},{2,7},{9,0,1,6}};
```

法三：

```java
int[][] arr;
arr = new int[][]{{1,2,3},{4,5,6},{7,8,9,10}};
```

1. 规则分配

```java
int m,n;
int[][] a = new int[m][n];
```

2. 不规则分配：从最高维开始，分别为每一维分配空间，例如：

```java
String[][] s = new String[2][];
s[0] = new String[2];
s[1] = new String[3];
```

二维数组的长度

```java
int[][] a = new int[2][3];
System.out.println(a.length);    //二维数组a的行数
System.out.println(a[0].length);  //二维数组第一行有多少个元素
```

### Arrays工具类

[Arrays (Java SE 17 & JDK 17) (oracle.com)](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Arrays.html)

java.util.Arrays类包含了用来操作数组（比如排序和搜索）的各种方法。

```java
// public static String toString(int[] arr):打印数组
int[] a = {1,2,3,4,5};
System.out.println(Arrays.toString(a));  // [1, 2, 3, 4, 5]

// public static int[] copyOfRange(int[] arr, int from, int to):下标[from,to)的元素塞入新数组
System.out.println(Arrays.toString(Arrays.copyOfRange(a, 0, 3))); // [1, 2, 3]

// public static int[] copyOf(int[] arr, int newlength):  指定一个新长度的数组，并将元素依次复制过去
System.out.println(Arrays.toString(Arrays.copyOf(a,10))); //[1, 2, 3, 4, 5, 0, 0, 0, 0, 0]
```

```java
int[] a = {1,3,2,4,5};
// public static void sort(int[] arr):在原数组上排序
Arrays.sort(a);
System.out.println(Arrays.toString(a));  //[1, 2, 3, 4, 5]
```



# 包机制

## 什么是包

所谓包，说白了就是文件夹或者目录，当我们创建了许多类时，就需要包来归类，可以将功能相似或相关的类放在同一包下，包里不能有同名类，但不同包下的类可以重名。所以，**包的本质其实就是存放类的文件夹**。

## 包的作用

1. 可以对类进行分门别类的管理，**把功能相似或相关联的类或接口放在同一包下，方便查看和使用。**

   <img src=javase.assets/1710054736120.png width=60% padding=20%>

   

   如上图所示，每一个文件夹就是一个包，每个包又有多个类。

2. 当同时调用两个不同包中相同类名的类时，应该加上包名加以区别。因此，**包可以避免名字冲突**。

   如果导入两个包里存在相同的类，在调用的时候需要具体指明调用哪个包里的类

   ```java
   import pack1.ClassA;
   import pack2.ClassA;
   
   
   pack2.ClassA s = new pack2.ClassA();
   ```

3. **限制访问权限**，java默认的访问权限是在本包下，用到其他包下的类需要导包。

   包的使用：

   ```java
   import pack.ClassA;  //导入pack包里的ClassA类
   import pack.*;        //导入pack包里所有的类
   ```

   当导入包类以后，可以通过类实例化对象，再通过对象调用类中具体实现方法了。

   ```java
   import java.util.Scanner;
   
   Scanner scan = new Scanner(System.in);   //实例化类Scanner
   String str = scan.nextline();        //调用scan中的方法nextline(),从键盘获取一串字符串并返回
   ```

package关键字的作用是声明当前类所在的包，因此**一个类中最多只有一个package语句，且必须放在类的最顶端**。

**import关键字指令，要放在包声明后，类定义前。**

> 面试题：
>
> 要导入java/awt/event下面的所有类，叙述正确的是？()
>
> A.    import java.awt.\*和import java.awt.event.*都可以
>
> B.    只能是import java.awt.event.*
>
> 正确答案:B
>
> import java.awt.\* 只是导入了java/awt该层下的所有类，java/awt下的子包的类不会导入。

# 面向对象

### 类和对象

#### 类和对象的概念

#### 类的成员

**fields 成员变量**

**Method (成员)方法**

static & instance 

static：不用创建实例就可调用。

instance：必须通过创建实例才能调用。

attribute：public fields

properties： private fields+ getter/setter方法

![1711634588140](javase.assets/1711634588140.png)

#### 使用举例

```java
//声明Animal类
public class Animal { //动物类
	public int legs;
	public void eat() {
	System.out.println("Eating.");
	}
	public void move() {
		System.out.println("Move.");
	}
}
```

```java
//声明测试类
public class AnimalTest {
	public static void main(String args[]) {
	//创建对象
	Animal xb = new Animal();
	xb.legs = 4;//访问属性
	System.out.println(xb.legs);
	xb.eat();//访问方法
	xb.move();//访问方法
	}
}
```

#### 匿名对象

如果一个对象只需要进行一次方法调用，那么就可以使用匿名对象。

```java
new Person().shout();   // new Person() 返回的是一个对象。
```

#### 对象的内存解析

对象名里存放的是对象的地址，对象本体存放在堆空间。

#### 成员变量

语法格式：

```java
[修饰符] class 类名{
	[修饰符] 数据类型 成员变量名 [= 初始化值];
}
```

说明：

- 必须在类中，方法外定义

- 修饰符
  常用的权限修饰符有：private、缺省、protected、public
  其他修饰符：static、final
- 初始化值
  根据情况，可以显式赋值；也可以不赋值，使用默认值



#### 成员变量 vs 局部变量

在方法体外，类体内声明的变量称为成员变量。
在方法体内部声明的变量称为局部变量。

> 由static修饰的成员变量又被称为静态变量，类变量。
>
> 非static修饰的成员变量，又被称为实例变量。

#### 方法(method)

**Java里的方法 不能独立存在 ，所有的方法必须定义在类里。**

方法的定义格式：

```java
[修饰符] 返回值类型 方法名([形参列表])[throws 异常列表]{
	//方法体;
}
```

- 修饰符：可选的。方法的修饰符也有很多，例如：public、protected、private、缺省、static、abstract、native、final、synchronized等，后面会一一学习。
  其中，根据是否有static，可以将方法分为静态方法和非静态方法。其中静态方法又称为类方法，非静态方法又称为实例方法。
  
- throws 异常列表：可选，在【异常处理】章节再讲

#### 方法调用内存解析

跟汇编语言，递归有关。栈，局部变量存放在栈里

#### 对象数组

#### 方法的重载

- 方法重载：在同一个类中，允许存在多个同名方法，只要它们的参数列表不同即可。参数列表不同，意味着参数个数或参数类型的不同
- 重载的特点：与修饰符、返回值类型无关，**只看参数列表**，且参数列表(参数个数或参数类型)必须不同。调用时，根据方法参数列表的不同来区别。



#### 可变个数的形参

**使用背景**

在调用方法的时候可能会需要方法的形参的类型是确定的，而参数的个数是不确定的，此时我们就可以使用可变个数的形参的机制来实现。

格式如下：

```java
void foo(String... args);
void foo(String[] args);
```

两种格式的作用是一样的。如果一个方法同时写了这两种格式不会被认为是重载，而是会出现编译错误。

注意：

- 可变参数只能作为函数的最后一个参数

- 由于可变参数必须是最后一个参数，所以一个函数最多只能有一个可变参数

- 在调用的时候，可以传递0、1、多个参数，当传递多个参数的时候，args在方法体中是数组名。

- 两种调用方法：

  ```java
  public void foo(String...args){}
  
  foo("arg1", "arg2", "arg3");
  
  //上述过程和下面的调用是等价的
  foo(new String[]{"arg1", "arg2", "arg3"});
  ```

  重载时优先匹配固定参数

  调用一个被重载的方法时，如果此调用既能够和固定参数的重载方法匹配，也能够与可变长参数的重载方法匹配，则选择固定参数的方法:

  ```java
  public class Varargs {
  
      public static void test(String... args) {
          System.out.println("version 1");
      }
  
      public static void test(String arg1, String arg2) {
          System.out.println("version 2");
      }
      public static void main(String[] args) {
          test("a","b");//version 2 优先匹配固定参数的重载方法
          test();//version 1
      }
  }
  ```

  匹配多个可变参数

  调用一个被重载的方法时，如果此调用能够和**两个可变长参数**的重载方法匹配，则编译出错:

  ```java
  public class Varargs {
  
      public static void test(String... args) {
          System.out.println("version 1");
      }
  
      public static void test(String arg1, String... arg2) { 
          System.out.println("version 2");
      }
      public static void main(String[] args) {
          test("a","b");//Compile error
      }
  }
  ```


### 封装

> 合理隐藏，合理暴露

Java实现封装是依赖权限修饰符来控制类或成员的可见性范围。

访问控制修饰符：

> java权限修饰符有四种：private、public、默认、protected
>
> 权限修饰符大小排序：public>protected>默认>private
>
> 我们分成两级介绍：
>
> 高一级：类和接口
>
> 低一级：类和接口的成员
>
> 
>
> 先介绍类和接口：
>
> 类和接口的权限修饰符有两个：public、默认
>
> public：所有包的所有类和接口可见。
>
> 默认：本包内的所有类和接口可见。
>
> 对于类和接口来说，可见性意味着可以声明。
>
> 
>
> 接下来介绍 接口的成员：
>
> 接口的成员的修饰符有两个：public、private
>
> public：所有包所有类和接口可见
>
> private：只有本接口可见
>
> 
>
> 对于成员来说，可见意味着可以访问。
>
> 
>
> 访问成员的方式本质上只有一种，即通过`变量名.成员名`访问。本质上还是用的this访问。
>
> this、super的访问路径：就近往上找原则。
>
> 
>
> 接下来介绍类的成员：
>
> 类的成员有成员变量、成员方法、构造器、代码块、内部类。
>
> 其中代码块不能被权限修饰符修饰。
>
> 
>
> 类的成员的权限修饰符：private、public、默认(package-private)、protected
>
> 对于成员的可见性，指的是可访问。
>
> private：本类内可见
>
> public：所有包的所有类和接口可见
>
> 默认：本包内可见。
>
> protected：
>
> 在父类内定义一个protected成员，**在父类所在的包内**，无论是定义父类对象、与父类同一个包下的子类对象，还是不同包下的子类对象，都可以访问protected成员。即保持默认权限。除此之外，**在其他包的子类内**，只有子类对象能访问protected成员。

### 构造器

构造器就是c++中的构造函数

构造器的作用：

**在new一个类的一个对象的时候会自动调用该类的构造器,完成对类的对象的初始化。**

```java
[修饰符] class 类名{
	[修饰符] 构造器名(参数列表){
	// 实例初始化代码
	}
}
```

说明：

1. 构造器名必须与它所在的类名必须相同。
2. 它没有返回值，所以不需要返回值类型，也不需要void。
3. 构造器的修饰符只能是权限修饰符，不能被其他任何修饰。比如，不能被static、final、synchronized、abstract、native修饰，不能有return语句返回值。

使用说明：

1. 当我们没有显式的声明类中的构造器时，系统会默认提供一个无参的构造器并且该构造器的修饰符默认与类的修饰符相同

  ![1708074190069](javase.assets/1708074190069.png)

2. 当我们显式的定义类的构造器以后，系统就不再提供默认的无参的构造器了。

3. 在类中，至少会存在一个构造器。

4. 构造器是可以重载的。

### this

采用 **this** 关键字是为了解决实例变量和局部变量之间发生的同名的冲突。

**在实例方法或构造器中，如果使用当前类的成员变量或成员方法可以在其前面添加this，增强程序的可读性。不过，通常我们都习惯省略this。**

但是，当形参与成员变量同名时，如果在方法内或构造器内需要使用成员变量，必须添加this来表明该变量是类的成员变量。即：我们可以用this来区分`成员变量`和`局部变量`。比如：

![1708077528244](javase.assets/1708077528244.png)

> this关键字=**该类的当前对象的地址**。

this在构造器中的特殊用法：

this( ) 用来访问本类的构造方法，下面定义一个 Student 类，使用 this( ) 调用构造方法给 name 赋值：

```java
public class Student {
    String name;
    // 无参构造方法（没有参数的构造方法）
    public Student() {
        this("张三");    //
    }
    // 有参构造方法
    public Student(String name) {
        this.name = name;
    }
    // 输出name和age
    public void print() {
        System.out.println("姓名：" + name);
    }
    public static void main(String[] args) {
        Student stu = new Student();
        stu.print();       //张三
    }
}
```

注意：

- this( ) 不能在普通方法中使用，只能写在构造方法中。
- 在构造方法中使用时，必须是第一条语句。



### JavaBean

要求：所有的成员属性必须是private，并为每一个成员属性创建get/set方法，用于对私有属性的访问/赋值。必须有一个无参构造器。

```java
public class Person{
    private String name;
    private int age;

    public int getAge(){
      return age;
    }

    public String getName(){
      return name;
    }

    public void setAge(int age){
      this.age = age;
    }

    public void setName(String name){
      this.name = name;
    }
}
```

### 继承

继承就是子类继承父类的特征和行为

```java
class 父类 {
}
 
class 子类 extends 父类 {
}
```

为什么要继承？

继承可以减少代码的复用，有利于功能的扩展，继承是多态的前提，没有继承就没有多态。

需要注意的是 `Java类`不支持多继承，但支持多重继承。

<img src=javase.assets/1706181651666.png width=60%>

- 子类继承父类所有的属性、方法。---本质上都是父类的。实际上通过this、super一层层向上查找。
- 子类可以拥有自己的属性和方法，即子类可以对父类进行扩展。
- 父类的构造方法不能继承，需要子类实现自己的构造方法。在子类的构造方法体中第一条语句必须是调用父类的构造方法
- 提高了类之间的耦合性(继承的缺点，耦合度高就会造成代码之间的联系越紧密，代码独立性越差)



### 重写方法

重写是子类对父类的允许访问的方法的实现过程进行重新编写, 返回值和形参都不能改变。**即外壳不变，核心重写！**

```java
class Animal{
   public void move(){
      System.out.println("动物可以移动");
   }
}
 
class Dog extends Animal{
   public void move(){
      System.out.println("狗可以跑和走");
   }
}
 
public class TestDog{
   public static void main(String args[]){
      Animal a = new Animal(); // Animal 对象
      Animal b = new Dog(); // Dog 对象
 
      a.move();// 执行 Animal 类的方法
 
      b.move();//执行 Dog 类的方法
   }
}
```

**方法的重写规则**

- 父类的成员方法只能被它的子类重写。

- 父类被重写的方法名和参数列表必须与子类要重写的方法名和参数列表相同。

- **子类重写的方法的权限修饰符大于等于父类被重写方法的权限修饰符**

- 关于返回值类型：

  父类要被重写的方法分返回值如果是void，子类重写方法的返回值也必须是void

  父类要被重写的方法分返回值如果是基本数据类型，那么父类方法返回值是啥，子类方法返回值就是啥。

  父类要被重写的方法分返回值如果是引用数据类型，那么父类方法返回值是啥，子类方法返回值就是啥或者是它的子类。

- **如果父类要被重写的方法抛出了异常，那么子类重写方法也要抛出相同的异常或其子类异常。**如果父类要被重写的方法没有抛出异常，子类重写方法也不能抛异常。

- 声明为 final 的方法不能被重写。

- 声明为 static 的方法不能被重写，因为static方法是属于类的。但是可以在子类中定义一个同名的static方法，这个方法是属于子类的。

- 构造方法不能被重写。

> @Override使用说明：
>
> 写在方法上面，用来检测是不是满足重写方法的要求。这个注解就算不写，只要满足要求，也是正确的方法覆盖重写。建议保留，这样编译器可以帮助我们检查格式，另外也可以让阅读源代码的程序员清晰的知道这是一个重写的方法。

### 重写变量

父类中有一变量名，如果子类又新定义了一个同名的变量，其实跟重写方法是一样的。父类被重写的方法或变量，在子类中可以通过super访问。而子类新定义的同名方法或变量在子类中可以通过this访问。如果没有在子类中定义同名方法或变量，那么父类的方法或变量用this就能访问。就是就近往上原则。

**<font color='red'>特别说明：应该避免子类声明和父类重名的成员变量</font>**

### super

思考两个问题：

1. 如果子类重写了父类的一个方法，还能不能再调用父类被重写前的方法？

可以，在子类中使用`super.方法名`即可

```java
// Father.java
public class Father {
    void show(){
        System.out.print("I am Father.");
    }
}
```

```java
// son.java
public class Son extends Father{
    @Override
    void show(){
        System.out.print("I am son.");
    }
    void showFather(){
        super.show();          //调用父类被重写前的方法
    }
}
```

```java
// Main.java
public class Main {
    public static void main(String[] args){
        Son s = new Son();
        Son.show();            // I am son.
        Son.showFather();      //  I am Father.
    }
}
```



总结：

- **方法前面没有super.和this.**，默认是this.
  - 先从本类找匹配方法，如果没有，再从直接父类找，再没有，继续往上                                              
- **方法前面有super.**
  - 从本类的直接父类找，如果没有，继续往上追溯

2. 父类中有一变量名，继承给子类之后，如果子类又新定义了一个同名的变量，会怎么样？

```java
// Father.java
public class Father {
    int i = 0;
}
```

```java
// son.java
public class son extends Father{
    int i = 1;
    void showFatheri(){
        System.out.print("Father's i = "+super.i); //调用父类的属性i
    }
}
```

```java
// Main.java
public class Main {
    public static void main(String[] args) {
        son s = new son();
        System.out.print(s.i);  // 1
        s.showFatherI();        // Father's i = 0
    }
}
```

- **变量前面没有super.和this.**
  - 在构造器、代码块、方法中如果出现使用某个变量，先查看是否是当前块声明的`局部变量`，
  - 如果不是局部变量，先从当前执行代码的`本类去找成员变量`
  - 如果从当前执行代码的本类中没有找到，会往上找`父类声明的成员变量`（权限修饰符允许在子类中访问的）
- **变量前面有this.** 
  - 通过this找成员变量时，先从==本类去找成员变量==
  - 如果从当前执行代码的本类中没有找到，会往上找==父类声明的成员变量（==权限修饰符允许在子类中访问的）
- **变量前面super.** 
  - 通过super找成员变量，直接从本类的直接父类去找成员变量（权限修饰符允许在子类中访问的）
  - 如果直接父类没有，接着网上找（权限修饰符允许在子类中访问的）

在阿里的开发规范等文档中都做出明确说明：

<img src=javase.assets/1708155730943.png width=60%>

**子类构造器中调用父类构造器**

① 子类继承父类时，不会继承父类的构造器。只能通过“super(形参列表)”的方式调用父类指定的构造器。

② 规定：“super(形参列表)”，必须声明在构造器的首行。

③ 我们前面讲过，在构造器的首行可以使用"this(形参列表)"，调用本类中重载的构造器，
     结合②，结论：在构造器的首行，"this(形参列表)" 和 "super(形参列表)"只能二选一。

④ 如果在子类构造器的首行既没有显示调用"this(形参列表)"，也没有显式调用"super(形参列表)"，
​     则子类此构造器默认调用"super()"，即调用父类中空参的构造器。

⑤ 由③和④得到结论：子类的任何一个构造器中，要么会调用本类中重载的构造器，要么会调用父类的构造器。
     只能是这两种情况之一。

⑥一个类中声明的所有构造器中至少有一个构造器调用父类的构造器。

> 开发中常见错误：
>
> 如果子类构造器中既未显式调用父类或本类的构造器，且父类中又没有空参的构造器，则`编译出错`。

面试题：以下程序输出的结果是什么？

```java
class Test {
    public static void main(String[] args) {
        System.out.println(new B().getValue());
    }
    static class A {
        protected int value;
        public A (int v) {
            setValue(v);
        }
        public void setValue(int value) {
            this.value= value;
        }
        public int getValue() {
            try {
                value ++;
                return value;
            } finally {
                this.setValue(value);
                System.out.println(value);
            }
        }
    }
    static class B extends A {
        public B () {
            super(5);
            setValue(getValue()- 3);
        }
        public void setValue(int value) {
            super.setValue(2 * value);
        }
    }
}
----------output---------
22
34
17    
```

> **第一个数值**
>
>  new B()构造B类实例对象，进入B类的构造方法，B类构造方法的第一行代码用super(5)调用了父类带有参数的构造函数，父类的构造函数又调用了setValue()方法，但值得注意的是，**子类中的方法覆盖父类的方法以后，由于向上转型，父类调用的方法实际上是子类的**。那么这里的setValue(v);调用了B类的setValue()方法，而B类中setValue()方法又使用**super**关键字调用了父类的setValue()方法，将B实例的value值设置为2 x 5 = 10。那么到这里，B类的构造函数中第一行代码super(5)执行完毕，程序继续向下执行进入setValue(getValue()- 3);代码块。
>
> \2.  这里先执行getValue()方法，但因为B类中并没有重写该方法，这里需要调用父类的getValue()方法。进入A类getValue()方法，首先是value++，那么此时B的成员变量value值由 10变为11，程序继续向下执行，将11作为返回值，但此处要注意的一点是，在**Try catch finally体系当中，在return之前始终会执行finally里面的代码，如果finally里面有return，则数据跟随finally改变。如果没有return，则原数据不跟随finally里改变的数据改变。**那么进入finally代码块，由于此时正在初始化的是B类的一个对象（运行时多态），因此调用B类的setValue()方法。B类的setValue()方法中使用**super**关键字调用了父类的setValue()方法，将原有的value*2，即11 x 2 = 22，继续向下进行System.out.println(value);输出第一个数值22。随后，A类的getValue()方法将之前暂存的value=11返回。
>
> **第二个数值**
>
> \1.  拿到getValue()方法返回值之后程序继续运行，此处代码变为setValue(11- 3);根据和之前相同的流程，B类成员变量value的值变为16。程序运行到此处，new B()执行完毕。
>
> \2.  回到main函数中，实例化的B类对象调用getValue()方法，B类中并没有重写该方法，需要调用父类的getValue()方法。getValue()方法第一行代码value++将B的成员变量value值变为17，此时执行到return代码，将value=17暂存，等待finally代码块运行完毕后返回。
>
> \3.  此处finally代码块执行流程和之前相同，这里不再赘述。那么执行完this.setValue(value);后，value值变为2 x 17 = 34。继续向下进行System.out.println(value);输出第二个数值34，return刚刚暂存的value=17。
>
> **第三个数值**
>
> 回到main函数，将刚刚返回的值输出，就得到了第三个数值17。

### 子类对象实例化过程

当你创建(new)一个对象时，Java虚拟机会为对象分配内存空间并加载该类的字节码文件到内存中。

类的加载是动态的，即当需要使用某个类时才会进行加载。

在new子类对象时，Java虚拟机会首先看构造器的第一条语句是调用了父类构造器还是当前类构造器，如果是当前类构造器则调用该构造器。如果是父类构造器，则看父类字节码文件是否加载在内存中，如果没有加载到内存，则将父类加载到内存再调用该构造器。

[98-面向对象(进阶)-子类对象实例化的全过程_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1PY411e7J6?p=98&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

TODO





```java
public class P {
    public static int abc = 123;
    static{
        System.out.println("P is init");
    }
}
public class S extends P {
    static{
        System.out.println("S is init");
    }
}
public class Test {
    public static void main(String[] args) {
        System.out.println(S.abc);
    }
}
----------------

P is init
123    
```

**这种情况，没有加载子类到内存，因为没有调用构造器。**TODO:不理解，这个应该看JVM才能理解。

### 多态

多态是同一个行为具有多个不同表现形式或形态的能力。

多态存在的三个必要条件

- 继承

- 重写

- 父类引用指向子类对象：**Parent p = new Child();**

  > new Child()返回一个Child类的对象，然后将该子类对象赋值给父类变量。

```java
package com.atguigu.polymorphism.grammar;

public class Pet {
    private String nickname; //昵称

    public String getNickname() {
        return nickname;
    }

    public void setNickname(String nickname) {
        this.nickname = nickname;
    }

    public void eat(){
        System.out.println(nickname + "吃东西");
    }
}
```

```java
package com.atguigu.polymorphism.grammar;

public class Cat extends Pet {
    //子类重写父类的方法
    @Override
    public void eat() {
        System.out.println("猫咪" + getNickname() + "吃鱼仔");
    }

    //子类扩展的方法
    public void catchMouse() {
        System.out.println("抓老鼠");
    }
}
```

```java
package com.atguigu.polymorphism.grammar;

public class Dog extends Pet {
    //子类重写父类的方法
    @Override
    public void eat() {
        System.out.println("狗子" + getNickname() + "啃骨头");
    }

    //子类扩展的方法
    public void watchHouse() {
        System.out.println("看家");
    }
}
```

**1、方法内局部变量的赋值体现多态**

```java
package com.atguigu.polymorphism.grammar;

public class TestPet {
    public static void main(String[] args) {
        //多态引用
        Pet pet = new Dog();
        pet.setNickname("小白");
        
        //多态的表现形式
        /*
        编译时看父类：只能调用父类声明的方法，不能调用子类扩展的方法；
        运行时，看“子类”，如果子类重写了方法，一定是执行子类重写的方法体；
         */
        pet.eat();//运行时执行子类Dog重写的方法
//      pet.watchHouse();//不能调用Dog子类扩展的方法

        pet = new Cat();
        pet.setNickname("雪球");
        pet.eat();//运行时执行子类Cat重写的方法
    }
}
```

**2、方法的形参声明体现多态**

```java
package com.atguigu.polymorphism.grammar;

public class Person{
    private Pet pet;
    public void adopt(Pet pet) {//形参是父类类型，实参是子类对象
        this.pet = pet;
    }
    public void feed(){
        pet.eat();//pet实际引用的对象类型不同，执行的eat方法也不同
    }
}
```

```java
package com.atguigu.polymorphism.grammar;

public class TestPerson {
    public static void main(String[] args) {
        Person person = new Person();

        Dog dog = new Dog();
        dog.setNickname("小白");
        person.adopt(dog);//实参是dog子类对象，形参是父类Pet类型
        person.feed();

        Cat cat = new Cat();
        cat.setNickname("雪球");
        person.adopt(cat);//实参是cat子类对象，形参是父类Pet类型
        person.feed();
    }
}
```

**3、方法返回值类型体现多态**

```java
package com.atguigu.polymorphism.grammar;

public class PetShop {
    //返回值类型是父类类型，实际返回的是子类对象
    public Pet sale(String type){
        switch (type){
            case "Dog":
                return new Dog();
            case "Cat":
                return new Cat();
        }
        return null;
    }
}
```

```java
package com.atguigu.polymorphism.grammar;

public class TestPetShop {
    public static void main(String[] args) {
        PetShop shop = new PetShop();

        Pet dog = shop.sale("Dog");
        dog.setNickname("小白");
        dog.eat();

        Pet cat = shop.sale("Cat");
        cat.setNickname("雪球");
        cat.eat();
    }
}
```

### 实例属性没有多态

因为多态的定义就是同一个**行为**具有不同的能力。

编译时看左边，左边是父类对象，因此父类对象只能调用父类的属性，不能调用子类属性。

### instanceof 运算符

instanceof是Java中的二元运算符，左边是对象，右边是类或接口；当对象是右边类或子类所创建对象时，返回true；否则，返回false。从英语的角度也很容易理解的啊，比如"Mike" is intance of String 这句话是对的。"Mike"是String的实例

```java
boolean result = "Mike" instanceof String; // 由于 "Mike" 是 String类的对象，所以返回true
boolean result = "Mike" instanceof String; // 由于 "Mike" 是 Object类的子类String对象，所以返回true
```

### 类型转换

使用父类变量接收了子类对象之后，我们就`不能调用`子类拥有，而父类没有的方法了。这很正常啊，因为你变量是父类类型的。所以，想要调用子类特有的方法，必须做类型转换

<img src=javase.assets/1708532682100.png width=60% align=left>

```java
package com.atguigu.polymorphism.grammar;

public class ClassCastTest {
    public static void main(String[] args) {
        //没有类型转换
        Dog dog = new Dog();

        Pet pet = new Dog();//向上转型
        pet.setNickname("小白");
        pet.eat();//可以调用父类Pet有声明的方法eat，但执行的是子类重写的eat方法体
//        pet.watchHouse();//不能调用父类没有的方法watchHouse

        Dog d = (Dog) pet;  //向下转型
        System.out.println("d.nickname = " + d.getNickname());
        d.eat();//可以调用eat方法
        d.watchHouse();//可以调用子类扩展的方法watchHouse

        Cat c = (Cat) pet;//编译通过，因为从语法检查来说，pet的编译时类型是Pet，Cat是Pet的子类，所以向下转型语法正确
        //但是这句代码运行报错ClassCastException，因为pet变量存储的对象是Dog，Dog和Cat之间是没有继承关系的
        //为了避免出现这种运行时异常，我们在向下转型的前要用instanceof先判断一下。
        if(pet instanceof Cat) {  // 如果pet是Cat类型或Cat子类类型，才能转型。
            Cat c = (Cat) pet
        }
    }
}
```

### Object类的使用

类 `java.lang.Object`是Java所有类的根类。如果一个类没有特别指定父类，那么默认则继承自Object类。

<img src=javase.assets/1708605856462.png width=60%>

```java
public class Person {
	...
}
//等价于：
public class Person extends Object {
	...
}
```

如果形参类型或返回值类型是Object类，那么任意类的对象都可以作为实参或者返回值。（多态！）

```java
method(Object obj){…} //可以接收任何类

Person o = new Person();  
method(o);
```

#### Object类的方法

根据JDK源代码及Object类的API文档，Object类当中包含的方法有11个。这里我们主要关注其中的6个：

`equals()`

**= =：** 

- 基本类型比较值:两个变量的值相等，即为true。

- 引用类型比较地址(是否指向同一个对象)：指向同一个对象时，返回true。

**equals()：**所有类都继承了Object，也就获得了equals()方法。还可以重写。Object类中equals方法同一个对象返回true

![1708606319312](javase.assets/1708606319312.png)

特例：当用equals()方法进行比较时，对类File、String、Date及包装类（Wrapper Class）来说，是比较类型及内容而不考虑引用的是否是同一个对象；

- 原因：在这些类中重写了Object类的equals()方法。

有兴趣可以看看源码



toString()

object类中的toString方法

```java
public String toString() {
    return getClass().getName() + "@" + Integer.toHexString(hashCode());
}
```

可以看到该方法不接受任何参数。

```java
public class Main {
    public static void main(String[] args) {
        Base b = new Base();
        //实际上，如果我们直接System.out.println(对象)，默认会自动调用这个对象的toString()；👇
        System.out.println(b.toString());  // 输出： Base@1b6d3586
        System.out.println(b);        // 输出： Base@1b6d3586
    }
}
class Base{}
```

返回值是 `类名@16进制地址值`

就是因为 `直接System.out.println(对象)，默认会自动调用这个对象的toString()；`这句话，toString方法才会这么重要，因为我们经常要打印查看对象。

在String、File、Date或包装类中对toString()方法进行了重写，此时返回值是对象的具体内容。

```java
public class Main {
    public static void main(String[] args) {
        String s = "hello";
        System.out.println(s.toString());   // 输出： hello
    }
}
```



在实际开发中，我们更希望输出对象的某些内容，因此要在子类中重写toString()方法



clone()

clone()方法是创建一个一模一样的对象，即深拷贝。

```java
// 下面是Object类中定义的clone()方法
protected native Object clone() throws CloneNotSupportedException;
```

可以看到该方法被protected修饰，
protected修饰的成员在包内的任意地方可以访问，在其他包的子类内可以访问。

```java
public class Main {
    public static void main(String[] args) {
        Object o = new Object();
        Object o1 = o.clone();   // 编译不通过。
        // 原因是Object类在java.lang包内，该Main不在java.lang包内，因此被protected修饰的clone()方法不能在其他包里的类内通过该对象直接调用。因此编译不通过。
    }
}
```

Main是Object的子类，Main类内是可以访问到clone()方法的。

```java
public class Main implements Cloneable{
    public static void main(String[] args) throws CloneNotSupportedException {
        Main m = new Main();
        Main m1 = (Main)m.clone();
        System.out.println(m1 == m);  // false
    }
}
```

正确使用clone()的方法：

比如，我们要实现Person类对象的深拷贝：

1. 让Person类实现Cloneable接口，该接口内没有任何成员，即是个空接口。为什么要这样做呢？相当于一个声明，声明该类可以进行深拷贝。没有该声明就算重写了clone()方法也不能用。
2. 重写clone()方法，记得抛异常。因受protected的限制，这里重写该方法实际上还是调用父类的clone()方法。相当于一个媒介。

```java
public class Person implements Cloneable{
    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}
```

```java
public class Main {
    public static void main(String[] args) throws CloneNotSupportedException {// 这里记得抛异常
        Person p = new Person();
        Person p1 =  (Person) p.clone();
        System.out.println(p == p1);     // false
    }
}
```

#### native关键字

TODO，这个应该看JVM的课程才能理解。

### Objects类的使用

Objects类是一个工具类，提供了很多操作对象的静态方法给我们使用。

介绍一个重要的方法：

```java
public static boolean equals(Object a, Object b) {
    return (a == b) || (a != null && a.equals(b));
}
```

选择Objects.equals(a,b);   而不选择a.equals(b);  是因为a可能是null。







### static

**如果想让一个成员变量被类的所有实例对象所共享，就用static修饰即可，称为类变量（或类属性）**

**在类中声明的实例方法，在类的外面必须要先创建对象，才能调用。但是有些方法不需要创建对象就可以调用，被static修饰，称类方法**

类变量、类方法，也称为静态变量、静态方法。

在Java类中，可用static修饰**属性、方法、代码块、内部类**

#### 静态变量

静态变量的特点

- 随着类的加载而初始化

- 静态变量在内存空间只有一份，为所有对象共享
- 静态变量在本类中，可以在任意方法、代码块、构造器中直接使用。
- 如果权限修饰符允许，在其他类中可以通过“`类名.静态变量`”直接访问，也可以通过“`对象.静态变量`”的方式访问（但是更推荐使用类名.静态变量的方式）。
- 静态变量的get/set方法也静态的，当局部变量与静态变量`重名时`，使用“`类名.静态变量`”进行区分。

#### 静态方法

静态方法的特点

- 静态方法在本类的任意方法、代码块、构造器中都可以直接被调用。
- 只要权限修饰符允许，静态方法在其他类中可以通过“类名.静态方法“的方式调用。也可以通过”对象.静态方法“的方式调用（但是更推荐使用类名.静态方法的方式）。
- 在static方法内部只能访问类的static修饰的属性或方法。
- 静态方法可以被子类继承，但不能被子类重写，子类可以有同名的静态方法。如果有重名，使用“类名.”进行区别。
- 静态方法的调用都只看编译时类型(意思就是说静态方法没有多态)。
- 因为不需要实例就可以访问static方法，因此static方法内部不能有this，也不能有super。

> 面试题：
>
>
>   1.成员变量：编译和运行都参考左边。 
>
>  
>
>   2.成员函数（非静态）：编译看左边，运行看右边 
>
>  
>
>   3.静态函数：编译和运行都看左边。 
>
> 
>
> 成员变量和静态函数一样，就是如果父类有一份的话，子类再创建一个同名的，不会覆盖。两份都可以拿到，比如成员变量可以用this和super区分，静态函数可以用类名区分。
>
> 再次声明：多态指的是对象的行为有多种表示，而不是成员变量和类的行为



### 单例模式(Singleton)

**设计模式**是在大量的`实践中总结`和`理论化`之后优选的代码结构、编程风格、以及解决问题的思考方式。设计模式免去我们自己再思考和摸索,经典的设计模式共有23种。每个设计模式均是特定环境下特定问题的处理方法。

所谓类的单例设计模式，就是采取一定的方法保证对某个类**只存在一个对象实例**，并且该类只提供一个取得该对象实例的方法。

实现思路：

首先将`类的构造器的访问权限设置为private`，这样就不能用new操作符在类的外部产生类的对象了，这样就保证了不能随意创建类的对象了。但**在类内部仍可以new该类的对象**。

单例模式的两种实现方式：

饿汉式

```java
class Singleton {
    // 1.私有化构造器
    private Singleton() {
    }

    // 2.内部提供一个当前类的实例
    private static Singleton single = new Singleton(); 
    //看成是该类的一个属性，类的成员属性一般用private修饰
    //用static修饰是为了能被下面的static方法调用。
    
    // 3.提供公共的静态的方法，返回当前类的对象
    public static Singleton getInstance() {
        return single;
    }
    // 如果不用static方法的话，就必须用类的对象调用，但是我们已经封死了在类的外部创建类的对象的途径。因此     // 必须用static方法。
}
```

```java
// Main.java
public class Main{
    public static void main(String[] args){
        Singleton s = Singleton.getInstance(); //在类的外部获取类唯一的对象
    }
}
```



懒汉式

```java
class Singleton {
    // 1.私有化构造器
    private Singleton() {
    }
    // 2.内部提供一个当前类的实例
    private static Singleton single;
    // 3.提供公共的静态的方法，返回当前类的对象
    public static Singleton getInstance() {
        if(single == null) {
            single = new Singleton();
        }
        return single;
    }
}
```

饿汉式 vs 懒汉式

饿汉式：

- 特点：`立即加载`，即在使用类的时候已经将对象创建完毕。
- 优点：实现起来`简单`；没有多线程安全问题。
- 缺点：当类被加载的时候，会初始化static的实例，静态变量被创建并分配内存空间，从这以后，这个static的实例便一直占着这块内存，直到类被卸载时，静态变量被摧毁，并释放所占有的内存。因此在某些特定条件下会`耗费内存`。

懒汉式：

- 特点：`延迟加载`，即在调用静态方法时实例才被创建。
- 优点：实现起来比较简单；当类被加载的时候，static的实例未被创建并分配内存空间，当静态方法第一次被调用时，初始化实例变量，并分配内存，因此在某些特定条件下会`节约内存`。
- 缺点：在多线程环境中，这种实现方法是完全错误的，`线程不安全`，根本不能保证单例的唯一性。
  - 说明：在多线程章节，会将懒汉式改造成线程安全的模式。



### 代码块

格式：

```java
[修饰符] class 类{
	[static]{
        //代码块
    }
}
```

代码块是类的成员之一。代码块可以被static修饰。代码块的主要作用是进行初始化、预处理

静态代码块：

- 静态代码块中的代码会随着类的加载而执行，意味着只能执行一次。

- 不可以调用非静态的属性和方法。
- 一个类若有多个静态的代码块，那么按照从上到下的顺序依次执行。



非静态代码块：

- 除了调用非静态的结构外，还可以调用静态的变量或方法。
- 每次创建对象的时候，都会执行一次。且先于构造器执行。

**非静态代码块的意义**

如果多个重载的构造器有公共代码，并且这些代码都是先于构造器内的其他代码执行的，那么可以将这部分代码抽取到非静态代码块中，减少冗余代码。



### 类中属性赋值的顺序

```java
public class Main {
    public static void main(String[] args) {
        Base b = new Base();
        Base c = new Base();
    }
}
class Base{
    {
        System.out.println("非静态代码块");
    }
    static {
        System.out.println("静态代码块");
    }
    Base(){
        System.out.println("构造器");
    }
}

---------------------------
静态代码块
非静态代码块
构造器
非静态代码块
构造器    
```



根据输出可知：

在第一次创建类的对象的时候会先加载类到内存中，此时执行静态代码块。

在创建对象的时候先执行非静态代码块，然后执行构造器。

在第二次创建类的对象的时候，由于第一次创建对象的时候已经加载了类，因此不会再次加载类，因此不会再执行静态代码块。

上面的好理解，下面的不好理解，应该根子类对象实例化过程一起分析TODO

```java
public class Main {
    public static void main(String[] args) {
        Base b = new Base();
        Base c = new Base();
    }
}
class Base extends Father{
    {
        System.out.println("子类非静态代码块");
    }
    static {
        System.out.println("子类静态代码块");
    }
    Base(){
        System.out.println("子类构造器");
    }
}

class Father{
    {
        System.out.println("父类非静态代码块");
    }
    static{
        System.out.println("父类静态代码块");
    }
    Father(){
        System.out.println("父类构造器");
    }
}
-------------------
父类静态代码块                 
子类静态代码块
父类非静态代码块
父类构造器
子类非静态代码块
子类构造器
父类非静态代码块
父类构造器
子类非静态代码块
子类构造器    
```

在第一次创建对象的时候先看Base类是否加载内存，发现没有，因此执行Base类的构造器里隐式调用的父类构造器`"super();"`,在执行前看父类Father是否加载，发现没有，因此先将父类加载，此时执行Father类的静态代码块，然后再将子类加载到内存，此时执行Base类的静态代码块。然后开始创建对象，此时执行父类的非静态代码块和构造器。然后执行子类的非静态代码块和构造器，此时第一个对象创建完成。

在第二次创建对象的时候，由于此时已经将类加载到内存中了，就不再执行非静态代码块。在创建对象的时候先执行父类的非静态代码块和构造器，然后再执行子类的非静态代码块和构造器。

下面代码运行结果是？

```java
public class Test{
static{
   int x=5;
}
static int x,y;
public static void main(String args[]){
   x--;
   myMethod( );
   System.out.println(x+y+ ++x);
}
public static void myMethod( ){
  y=x++ + ++x;
 }
}
```

1. JVM加载class文件时，就会执行静态代码块，静态代码块中初始化了一个变量x并初始化为5，由于该变量是个局部变量，静态代码快执行完后变被释放。 

2. 申明了两个静态成员变量x，y，并没有赋初值，会有默认出值，int类型为0， 







### final

final 可以用来修饰变量、方法和类。

final修饰变量，一旦赋值，它的值就不能被修改，即常量，常量名建议使用大写字母。

final修饰方法，该方法不能被子类重写

final修饰类，不能被继承

### abstract

#### 抽象类

将某些共性的东西抽取出来交给抽象类。

**被abstract修饰的类称为抽象类。**   抽象类中不一定包含抽象方法，但包含抽象方法的类必须是抽象类 

**抽象类除了不能实例化对象之外，类的其它功能依然存在，成员变量、成员方法和构造方法的访问方式和普通类一样。**

**由于抽象类不能实例化对象，所以抽象类必须被继承，才能被使用。**也是因为这个原因，通常在设计阶段决定要不要设计抽象类。

> 抽象类中能不能有构造方法？能。虽然抽象类不能实例化，即不能直接调用抽象类中的构造方法，但是子类可以使用super调用抽象类的方法。
>

#### 抽象方法

如果你想设计这样一个类，该类包含一个特别的成员方法，该方法的具体实现由它的子类确定，那么你可以在父类中声明该方法为抽象方法。抽象方法只包含一个方法名，而没有方法体。方法名后面直接跟一个分号，而不是花括号。

```java
public abstract class Employee
{   
    public abstract double computePay();
   //其余代码
}
```

声明抽象方法会造成以下两个结果：

- 如果一个类包含抽象方法，那么该类必须是抽象类。抽象类不强制要求包含抽象方法。
- 任何子类必须重写父类的抽象方法，或者声明自身为抽象类。



我们之前说，类的成员的权限修饰符有四种：缺省、public、private、protected。

抽象方法也是类的成员，但是抽象方法的权限修饰符只有三种：缺省、public、protected。

即没有private，因为抽象方法是必须被继承下去才能使用的，而private要求只能在本类中使用，因此abstract和private不能组合使用。

#### 模板方法设计模式

抽象方法就是定义一个模板，是个共性的东西，然后各自的子类又有具体的差异。这就是抽象类和抽象方法的意义。



### 接口(interface)

- 接口主要用于对类的行为进行约束，你实现了某个接口就具有了对应的行为。抽象类主要用于代码复用，强调的是所属关系。
- 一个类只能继承一个类，但是可以实现多个接口。

#### 成员

接口也会被编译成.class文件，但一定要明确它并不是类，而是另外一种引用数据类型。

接口不能被实例化。

格式：

```java
[修饰符] interface 接口名{
    // 接口内容
}
```

接口内容：

如果是Java 7，接口中可以包含的内容：

1. 常量
2. 抽象方法

如果是Java 8，接口中额外包含的内容：

3. 默认方法
4. 静态方法

如果是Java 9，接口中额外包含的内容：

5. 私有方法



##### 抽象方法

接口中定义的抽象方法的修饰符必须是 `public abstract`

```java
public interface Abs{
    //修饰符可以选择性省略，但必须是 public abstract，即接口的默认权限修饰符是public
    //下面四种形式都是抽象方法
    public abstract void method1();
    abstract void method1();
    public void method2();
    void method3();
}
```



##### 抽象方法的使用

接口不能直接使用，必须有 `类` 实现 `接口`

格式：

```java
[修饰符] class 类名 implements 接口名{ 
    
}
```

该类称为该接口的实现类，接口的实现类必须重写接口的所有抽象方法。 如果实现类没有重写接口的所有抽象方法，该实现类必须是抽象类。

> 由于实现类必须重写接口的所有抽象方法或不重写也声明成抽象方法(这种情况，实现类也必须是抽象类)，不管怎样，实现类中与接口有关的所有方法必须是public：**接口实现类相当于子类，子类的访问权限是不能比父类小的。** 

然后创建类的对象，调用方法即可。

```java
// myInterface.java
public interface myInterface {         // 定义了一个接口
    public abstract void method1();    // 接口中定义了一个抽象方法
}
```

```java
// myInterfaceImp.java
public class myInterfaceImp implements myInterface{     //类实现接口

    @Override
    public void method1() {                     //实现类中实现接口的所有抽象方法
        System.out.println("实现类调用已重写的接口的抽象方法");
    }
}
```

```java
// Main.java

public class Main {
    public static void main(String[] args) {
        myInterfaceImp m = new myInterfaceImp();      // 创建类的对象
        m.method1();                                 // 调用方法
    }
}
```



接口不能被实例化。很容易理解，因为接口中有抽象方法。。。即使接口中没有抽象方法，也不能实例化。这跟抽象类是一个意思。我认为原因是，接口中一般都是含有抽象方法的，所以就规定接口不能实例化了。



##### 默认方法

默认方法(default method),也叫扩展方法 （extension method）

格式：

```java
public default 返回值类型 方法名(){   // 必须是public，public可以省略，default不能省略。
    // 方法体;
}
```

默认方法用于解决接口升级的问题

刚开始的时候，有一个接口和多个实现类，该接口中有一个抽象方法，现在需要对接口进行升级，即扩展一个方法，这个时候如果在接口中定义一个抽象方法的话，需要在每一个实现类中都重写，如果继承该接口的类太多了得话，这个升级过程的工作量会非常大，因此可以使用默认方法，在接口中定义默认方法，`implements`该接口的实现类都会继承该方法，如果实现类需要的话可以对该默认方法进行重写。

 **在实现类中重写该默认方法的时候不要错用default关键字作为权限修饰符了哦**

default不是权限修饰符，而是在接口内使用的关键字。



##### 静态方法

格式：

```java
public static 返回值类型 方法名(形参列表){      //必须是public,public可省略，static不能省略
    // 方法体;
}
```



使用： `接口名.方法名(实参列表);`



##### 私有方法

如果一个接口中定义的多个方法中有共同的部分，可以将该共同部分提取出来放到私有方法中。接口的私有方法不能继承，**只能在接口内部使用**。

私有方法分为两类：普通私有方法，静态私有方法。

普通私有方法解决默认方法中重复代码的部分。

静态私有方法解决静态方法中重复代码的部分。

格式：

```java
private [static] 返回值类型 方法名(参数列表){
    // 方法体;
}
```

##### 常量

接口中也能定义常量，格式如下：

```java
public static final 常量名 = 字面量;    
```

接口中的常量必须被public static final修饰，public static final可省略。

> 软要求：常量名全大写，如果含多个单词，单词间用下划线分隔



总结：

接口中的成员 的权限修饰符只有两种：public和private





#### 实现类的多继承

java类不允许多继承，但是类可以继承多接口



如果实现类所实现的多个接口中，存在同名的抽象方法，在实现类中只需重写一次即可。

如果实现类所实现的多个接口中，存在同名的默认方法，在实现类中必须重写该冲突的默认方法。

如果一个类继承父类中的方法，与继承的接口中的默认方法同名，那么在调用该方法的时候调用的是从父类继承来的方法。



#### 接口继承接口

下图是java类继承的特性，接口继承接口这四种方式都支持。

<img src=javase.assets/1706181651666.png width=50%>

在多继承中，

如果多个父接口含有同名的抽象方法，子接口只需实现一次即可。

如果多个父接口含有同名的默认方法， 子接口必须重写该默认方法。

> 与实现类的多继承唯一的区别就是，在子接口中重写默认方法的时候有default关键字，在实现类重写默认方法的时候需要自定义一个权限修饰符。因为在类中没有default关键字。



#### 接口的多态性

```java
接口 接口名 = new 接口实现类();
接口名.接口成员名;  // 多态性
// 不能调用实现类额外实现的成员哦。因为编译时类型是接口。
```



### 内部类

#### 什么是内部类

将一个类A定义在另一个类B里面，里面的那个类A就称为`内部类（InnerClass）`，类B则称为`外部类（OuterClass）`。

#### 为什么要声明内部类呢

具体来说，当一个事物A的内部，还有一个部分需要一个完整的结构B进行描述，而这个内部的完整的结构B又只为外部事物A提供服务，不在其他地方单独使用，那么整个内部的完整结构B最好使用内部类。

总的来说，遵循`高内聚、低耦合`的面向对象开发原则。

#### 内部类的分类

根据内部类声明的位置，我们可以分为：

<img src=javase.assets/1708624085792.png width=50% align = left>

成员内部类是外部类的成员。局部内部类是在方法中声明的类。

#### 成员内部类

语法格式：

```java
[修饰符] class 外部类名{
    [修饰符] [static] class 成员内部类名{
    }
}
```



静态内部类：

- 只能调用外部类的静态成员。
- 和外部类不同，内部类还可以被private、protected修饰
- 编译以后生成`外部类名$内部类名.class`字节码文件





1. 外部类内访问成员内部类的成员，需要“内部类.成员”或“内部类对象.成员”的方式
2. 成员内部类可以直接调用外部类的所有成员，一个层级的嘛，很容易理解的啦。



**如果一个内部类中含有静态变量或静态方法，则这个内部类必须被static修饰。**

1. static类型的属性和方法，在类加载的时候就会存在于内存中。
2. 要使用某个类的static属性或者方法，那么这个类必须要加载到jvm中。

基于以上两点，可以看出，如果一个非static的内部类如果具有static的属性或者方法，那么就会出现一种情况：内部类未加载，但是却试图在内存中创建static的属性和方法，这当然是错误的。原因：类还不存在，但却希望操作它的属性和方法。



#### 成员内部类的实例化

创建成员内部类对象

- 实例化静态内部类

```
外部类名.静态内部类名 变量 = 外部类名.静态内部类名();
变量.非静态方法();
```

- 实例化非静态内部类

```
外部类名 变量1 = new 外部类();
外部类名.非静态内部类名 变量2 = 变量1.new 非静态内部类名();
变量2.非静态方法();
```



#### 局部内部类

##### 非匿名局部内部类

语法格式：

```java
[修饰符] class 外部类名{
    [修饰符] 返回值类型  方法名(形参列表){
            [final/abstract] class 局部内部类名{
    	}
    }    
}
```

编译后有自己的独立的字节码文件，`外部类名$方法名编号局部内部类名.class`。



##### 匿名内部类

有时考虑到这个实现类是一次性的，那么我们给它取名字，就显得多余。那么我们完全可以使用匿名内部类的方式来实现，避免给类命名的问题。

```java
new 父类([实参列表]){     // new了一个该类的匿名子类的对象，这里的实参列表指明调用的是哪一个构造器
    重写方法...
}
```

```java
new 父接口(){      // new了一个该接口的匿名实现类的对象
    重写方法...
}
```

使用匿名内部类的对象直接调用方法：（这里只举了父接口的例子，可以补充父类的例子）

```java
interface A{
	void a();
}
public class Test{
    public static void main(String[] args){
    	new A(){
			@Override
			public void a() {
				System.out.println("aaaa");
			}
    	}.a();
    }
}
```



```java
interface A{
	void a();
}
public class Test{
    public static void main(String[] args){
    	A obj = new A(){           // 将匿名对象赋值给对象名
			@Override
			public void a() {
				System.out.println("aaaa");
			}
    	};
    	obj.a();
    }
}
```

匿名内部类的对象作为实参

```java
interface A{
	void method();
}
public class Test{
    public static void test(A a){
    	a.method();
    }
    
    public static void main(String[] args){
    	test(new A(){
			@Override
			public void method() {
				System.out.println("aaaa");
			}
    	});
    }   
}
```

> 面试题：
>
> 一个源文件中有几个类和接口，就会生成几个.class文件。这句话是对的，我们总结一下：
>
> 外部类和接口会生成`类名.class`和`接口名.class`
>
> 外部类和接口中定义的内部类会生成 `外部类名$内部类名.class`文件
>
> 方法中定义的局部内部类会生成`外部类名$方法名编号局部内部类名.class`文件

##### JDK8新特性

###### lambda表达式

lambda表达式**只能**简化`函数式接口`的匿名实现类。

函数式接口：只能有一种抽象方法的接口。

TODO

函数式接口可以用 注解 `@FunctionalInterface` 修饰。



```java
interface A{
	void a();
}
public class Test{
    public static void main(String[] args){
    	new A(){
			@Override
			public void a() {
				System.out.println("aaaa");
			}
    	}.a();
    }
}
```

```java
// 将上面的代码用lambda表达式替换：
interface A{
	void a(int i);
}
public class Test{
    public static void main(String[] args){
        A a = (i) -> {
            System.out.println("aaaa");
        };
        a.a(1);
    }
}
```

我们来看看是怎么简化的：

1. 根据A a = () -> {}; 中的 A 可以推导出 new A()
2. 因为接口A中只有一个抽象方法，所以该抽象方法的权限修饰符、返回值类型、形参类型和方法名是知道的，可以省。`()`不能省，`()`里的形参不能省啊。
3. 如果只有一个形参，那么`()`也可以省，多个形参就不能省了，因为分不清了就。
4. 重写方法的内容放到lambda表达式的大括号里。如果只有一行代码，可以省略大括号，如果省略了大括号就必须省略掉分号。此时，如果有return，也必须省略掉。



###### 方法引用

[10、JDK8新特性：方法引用、特定类型方法引用、构造器引用_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Cv411372m?p=128&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

看懂了点。就按他讲的记。

### 枚举类

- **枚举类型本质上也是一种类，只不过是这个类的对象是有限的、固定的几个，不能让用户随意创建。**
- 枚举类的例子举不胜举：
  - `星期`：Monday(星期一)......Sunday(星期天)
  - `性别`：Man(男)、Woman(女)
  - `月份`：January(1月)......December(12月)
  - `季节`：Spring(春节)......Winter(冬天)

TODO

枚举类的实现：

- 在JDK5.0 之前，需要程序员自定义枚举类型。
- 在JDK5.0 之后，Java支持`enum`关键字来快速定义枚举类型。



#### 定义枚举类（JDK5.0 之前）

在JDK5.0 之前如何声明枚举类呢？相当于单例模式的引申：

- `私有化`类的构造器，保证不能在类的外部创建其对象
- 在类的内部创建枚举类的实例。声明为：`public static final` ，对外暴露这些常量对象
- 对象如果有`实例变量`，应该声明为`private final`（建议，不是必须），并在构造器中初始化

```java
class Season{
    private final String SEASONNAME;//季节的名称
    private final String SEASONDESC;//季节的描述
    private Season(String seasonName,String seasonDesc){
        this.SEASONNAME = seasonName;
        this.SEASONDESC = seasonDesc;
    }
    public static final Season SPRING = new Season("春天", "春暖花开");
    public static final Season SUMMER = new Season("夏天", "夏日炎炎");
    public static final Season AUTUMN = new Season("秋天", "秋高气爽");
    public static final Season WINTER = new Season("冬天", "白雪皑皑");

    @Override
    public String toString() {
        return "Season{" +
                "SEASONNAME='" + SEASONNAME + '\'' +
                ", SEASONDESC='" + SEASONDESC + '\'' +
                '}';
    }
}
class SeasonTest{
    public static void main(String[] args) {
        System.out.println(Season.AUTUMN);
    }
}
```

#### 定义枚举类（JDK5.0 之后）

格式：

```java
【修饰符】 enum 枚举类名{
    常量对象列表
}
```

举例：

```java
enum Size { SMALL， MEDIUM，LARCE，EXTRA_LARGE };
Size s = Size.MEDTUM;
```

Size类型的变量只能存储这个类型声明中给定的某个枚举值，或者null值,null表示这个变量没有设置任何值。

- 枚举类的常量对象列表必须在枚举类的首行，因为是常量，所以建议大写。
- 列出的实例对象会自动添加 public static final 修饰。
- 如果常量对象列表后面没有其他代码，那么“；”可以省略，否则不可以省略“；”

格式：

```java
【修饰符】 enum 枚举类名{
    常量对象列表;
    
    对象的实例变量列表;
}
```

- 编译器给枚举类默认提供的是private的无参构造器，如果枚举类需要的就是无参构造，那就不需要声明，写常量对象列表时也不用加参数
- 如果枚举类需要的是有参构造器，那就需要手动定义，有参构造器的private可以省略，调用有参构造的方法就是在常量对象名后面加(实参列表)就可以。
- 枚举类默认继承的是java.lang.Enum类，因此不能再继承其他的类型。
- JDK5.0 之后，switch关键字就开始支持枚举类型，case后面可以写枚举常量名，无需添加枚举类作为限定。

举例：

```java
public enum SeasonEnum {
    SPRING("春天","春风又绿江南岸"),
    SUMMER("夏天","映日荷花别样红"),
    AUTUMN("秋天","秋水共长天一色"),
    WINTER("冬天","窗含西岭千秋雪");

    private final String seasonName;
    private final String seasonDesc;
    
    private SeasonEnum(String seasonName, String seasonDesc) {
        this.seasonName = seasonName;
        this.seasonDesc = seasonDesc;
    }
    public String getSeasonName() {
        return seasonName;
    }
    public String getSeasonDesc() {
        return seasonDesc;
    }
}
```

> 经验之谈：
>
> 开发中，当需要定义一组常量时，强烈建议使用枚举类。

#### enum中常用方法

```java
String toString(): 默认返回的是常量名（对象名），可以继续手动重写该方法！
    
static 枚举类型[] values():返回枚举类型的对象数组。该方法可以很方便地遍历所有的枚举值，是一个静态方法
    
static 枚举类型 valueOf(String name)：可以把一个字符串转为对应的枚举类对象。要求字符串必须是枚举类对象的“名字”。如不是，会有运行时异常：IllegalArgumentException。
    
String name():得到当前枚举常量的名称。建议优先使用toString()。
    
int ordinal():返回当前枚举常量的次序号，默认从0开始
```



#### 实现接口的枚举类

- 和普通 Java 类一样，枚举类可以实现一个或多个接口
- 若每个枚举值在调用实现的接口方法呈现相同的行为方式，则只要统一实现该方法即可。
- 若需要每个枚举值在调用实现的接口方法呈现出不同的行为方式，则可以让每个枚举值分别来实现该方法

语法：

```java
//1、枚举类可以像普通的类一样，实现接口，并且可以多个，但要求必须实现里面所有的抽象方法！
enum A implements 接口1，接口2{
	//抽象方法的实现
}

//2、如果枚举类的常量可以继续重写抽象方法!
enum A implements 接口1，接口2{
    常量名1(参数){
        //抽象方法的实现或重写
    },
    常量名2(参数){
        //抽象方法的实现或重写
    },
    //...
}
```

举例：

```java
interface Info{
	void show();
}

//使用enum关键字定义枚举类
enum Season1 implements Info{
	//1. 创建枚举类中的对象,声明在enum枚举类的首位
	SPRING("春天","春暖花开"){
		public void show(){
			System.out.println("春天在哪里？");
		}
	},
	SUMMER("夏天","夏日炎炎"){
		public void show(){
			System.out.println("宁静的夏天");
		}
	},
	AUTUMN("秋天","秋高气爽"){
		public void show(){
			System.out.println("秋天是用来分手的季节");
		}
	},
	WINTER("冬天","白雪皑皑"){
		public void show(){
			System.out.println("2002年的第一场雪");
		}
	};
	
	//2. 声明每个对象拥有的属性:private final修饰
	private final String SEASON_NAME;
	private final String SEASON_DESC;
	
	//3. 私有化类的构造器
	private Season1(String seasonName,String seasonDesc){
		this.SEASON_NAME = seasonName;
		this.SEASON_DESC = seasonDesc;
	}
	
	public String getSEASON_NAME() {
		return SEASON_NAME;
	}

	public String getSEASON_DESC() {
		return SEASON_DESC;
	}
}
```



### 包装类

为什么需要包装类？

基本数据类型的变量不是类的对象，而java在设计时，为了统一，将基本数据类型封装成封装类。

比如泛型、集合不支持基本数据类型

```java
ArrayList<int> arrayList = new ArrayList<>();  //报错，不支持基本数据类型
```

因此，我们可以将基本数据类型包装成类。

| 原始类型 | 包装类    |
| :------- | :-------- |
| byte     | Byte      |
| boolean  | Boolean   |
| char     | Character |
| double   | Double    |
| float    | Float     |
| int      | Integer   |
| long     | Long      |
| short    | Short     |

包装类与基本数据类型间的转换

**装箱：把基本数据类型转为包装类对象**，转为包装类的对象，是为了使用专门为对象设计的API和特性

**拆箱：把包装类对象拆为基本数据类型**，转为基本数据类型，一般是因为需要运算，Java中的大多数运算符是为基本数据类型设计的。比较、算术等

**自动装箱与拆箱：**由于我们经常要做基本类型与包装类之间的转换，从`JDK5.0 `开始，基本类型与包装类的装箱、拆箱动作可以自动完成。

```java
Integer obj1 = Integer.valueOf(4); // 装箱
int num1 = obj.intValue();        // 拆箱
Integer obj2 = 4;       // 自动装箱:基本数据类型的数据用包装类对象接收
int num2 = obj2;        // 自动拆箱:包装类对象用基本数据类型的变量接收
```

```java
public class Main {
    public static void main(String[] args) {
        add(1,2);         // 实参1 ，2是int类型，形参是Integer类型，传参的过程进行了自动装箱。
    }
    public static void add(Integer i1,Integer i2) {
        System.out.println(i1+i2);
    }
}
```



包装类常用API

以Integer为例:

```
valueof
parseInt
```

#### 缓存池

缓存池也称常量池，它事先存储一些常用数据，用于提高性能节省空间。大部分的包装类都实现了缓存池。

| 包装类    | 已缓存的对象 |
| --------- | ------------ |
| Byte      | -128~127     |
| Short     | -128~127     |
| Integer   | -128~127     |
| Long      | -128~127     |
| Float     | 没有         |
| Double    | 没有         |
| Character | 0~127        |
| Boolean   | true和false  |

> `Integer i = 4;` `Integer i = Integer.valueOf(4);`如果基本数据类型的值处在缓存范围内，则不会重新创建对象，而是使用缓存池中已事先创建好的对象。而`Integer m = new Integer(1);`new的对象在堆中，跟常量池中的不是同一个对象。

比如常量池中已缓存Integer对象的值是从-128到127，我们在下面自动装箱了两个值为1的包装类对象，1处在-128到127之间，一比较发现这俩是同一个对象,也就是常量池里已缓存的对象。

```java
Integer a = 1;
Integer b = 1;
System.out.println(a == b);//true

Integer a = Integer.valueOf(1);
Integer b = Integer.valueOf(1);
System.out.println(a == b);//true

```

而128不在-128到127之间，这俩128不是同一个对象。

```java
Integer i = 128;
Integer j = 128;
System.out.println(i == j);//false
```

```java
Integer m = new Integer(1);//新new的在堆中
Integer n = 1;//这个用的是缓冲的常量对象，在方法区
System.out.println(m == n);//false

Integer x = new Integer(1);//新new的在堆中
Integer y = new Integer(1);//另一个新new的在堆中
System.out.println(x == y);//false
```

```java
Double d1 = 1.0;
Double d2 = 1.0;
System.out.println(d1==d2);//false 比较地址，没有缓存对象，每一个都是新new的
```



#### 类型转换问题

当包装类与基本数据类型对比时，包装类会自动拆箱变为基本类型再进行比较

```java
Integer i = 1000;
double j = 1000;    // 这个double是基本数据类型
System.out.println(i==j);//true  会先将i自动拆箱为int，然后根据基本数据类型“自动类型转换”规则，转为double比较
```

```java
Integer i = 1000;
int j = 1000;
System.out.println(i==j);//true 会自动拆箱，按照基本数据类型进行比较
```

```java
Integer i = 1;
Double d = 1.0;          // 这个 Double是包装类
System.out.println(i==d);//编译报错，两个不同类的对象不能用==
```



#### 不可变对象

不可变对象(Immutable Object)：对象一旦被创建后，对象所有的状态及属性在其生命周期内不会发生任何变化。

从不可变对象的定义来看，其实比较简单，就是一个对象在创建后，不能对该对象进行任何更改。

String类、包装类对象是不可变对象。

# 异常

异常(Exception)

异常分为编译时异常和运行时异常。

**编译时异常**(checked异常、受检异常):在编写代码的时候，编译器就能明确指出当前代码`可能发生`异常，并要求程序员提前编写如果异常发生了该怎样处理的代码。如果程序员`没有编写`对应的异常处理代码，过不去编译。例如：FileNotFoundException（文件找不到异常）。

<img src=Javase.assets/1716371432762.png width=60%>

这是Object类的clone方法，编译器明确告诉我们，clone方法在使用的时候**可能**会发生`java.lang.CloneNotSupportedException`这个异常。这个时候需要我们程序员对这个可能发生的异常进行处理。如果确实发生了这个异常该怎么处理(我们接下来会详细介绍`异常处理`)。

**运行时异常**（runtime异常、unchecked异常、非受检异常）：编译器发现不了，到了代码运行到出错的地方发生了异常。

**java.lang.RuntimeException**类及其子类都是运行时异常。比如：`ArrayIndexOutOfBoundsException`：数组下标越界异常，`ClassCastException`类型转换异常。除0发生的异常。这些都是真正发生了才会被发现的异常。**运行时异常虚拟机会帮我们捕获抛出最终呈现的就是输出在终端的错误信息。**



对于上述两种异常，我们程序员只需处理编译时异常即可，编译时异常需要处理了才能过编译，这个我们必须处理。而运行时异常需要程序执行后才能被发现，那时候我们只需根据返回的错误信息定位bug，修bug即可。

处理异常的两种方式：

方式一：try-catch-finally

方式二：throws + 异常类型

```java
public class Main implements Cloneable{
    public static void main(String[] args) throws CloneNotSupportedException {
        Main m = new Main();
        Main m1 = (Main)m.clone();
        System.out.println(m1 == m);  // false
    }
}
```

这是我们刚才举的编译时异常的例子，我们之前讲clone方法的时候是直接在 调用 `可能产生异常的该方法` 的方法声明上直接 `throws CloneNotSupportedException`，直接将这个异常给抛出去了。其实这是消极的处理异常的方法，因为我们刚才说，我们程序员需要处理的是：如果真发生了这个异常，该怎么处理。只抛出去就相当于，如果出现了这个异常，就把这个异常交给调用者，实际上这个异常还是没有被处理。那为什么我们可以这样写呢？因为我们知道我们写的这个程序，不会让它真发生这个异常，也就走不到处理这个异常的那一步。

如果我们把异常层层往上抛而不处理的话，到最后会把异常抛给main函数，如果main函数也不处理再往上抛的话，main函数最后再抛给JVM程序了，如果真出现了这个异常，那就跟运行时异常一样，JVM就会把异常信息被输出到控制台了。

```java
修饰符 返回值类型 方法名(参数) throws 异常类名1,异常类名2…{   }	
```

如果在编写方法体的代码时，某句代码可能发生某个`编译时异常`，不处理编译不通过，但是不想在当前方法体中处理，则此方法应`显式地`声明抛出异常，表明该方法将不对这些异常进行处理，而是将异常抛给该方法的调用者。

真正处理异常的是try-catch-finally

```java
try{
	......	//可能产生异常的代码
}
catch( 异常类型1 e ){
	......	//当产生异常类型1型异常时的处置措施
}
catch( 异常类型2 e ){
	...... 	//当产生异常类型2型异常时的处置措施
}  
finally{
	...... //无论是否发生异常，都无条件执行的语句
} 
```

**整体执行过程：**

当某段代码可能发生异常，不管这个异常是编译时异常（受检异常）还是运行时异常（非受检异常），我们都可以使用try块将它括起来，并在try块下面编写catch分支尝试捕获对应的异常对象。

> 你如果不对运行时异常进行处理，那么出现运行时异常之后，要么是线程中止，要么是主程序终止。 如果不想终止，则**必须捕获所有的运行时异常**，决不让这个处理线程退出。

- 如果在程序运行时，try块中的代码没有发生异常，那么catch所有的分支都不执行。
- 如果在程序运行时，try块中的代码发生了异常，根据异常对象的类型，将从上到下选择**第一个**匹配的catch分支执行。**此时try中发生异常的语句，其下面的代码将不执行**，而整个try...catch之后的代码可以继续运行。
- 如果在程序运行时，try块中的代码发生了异常，但是所有catch分支都无法捕获这个异常，那么JVM将会终止当前方法的执行，并把异常对象“抛”给调用者。

注意：

1. 如果有多个catch分支，并且多个异常类型有父子类关系，必须保证小的子异常类型在上，大的父异常类型在下。否则，报错。

2. **因为异常会引发程序跳转，从而会导致try中发生异常的语句下面的代码执行不到。**而程序中有一些特定的代码无论异常是否发生，都`需要执行`。例如，数据库连接、输入流输出流、Socket连接、Lock锁的关闭等，这样的代码通常就会放到finally块中。所以，我们通常将一定要被执行的代码声明在finally中。

   ```java
   public void readFile(String file)  throws FileNotFoundException,IOException {
   	// 读文件的操作可能产生FileNotFoundException或IOException类型的异常，因此在方法声明那一行抛出了     // 这俩异常
   	FileInputStream fis = new FileInputStream(file);
   }
   ```



  先来看一段代码：

```java
public abstract class Test {     
    public static void main(String[] args) {         
        System.out.println(beforeFinally());     
    }          
    public static int beforeFinally(){         
        int a = 0;         
        try{             
            a = 1;             
            return a;         
        }
        finally{             
            a = 2;
        }     
    } 
} 
/**output: 1 */
```

从结果上看，貌似`finally` 里的语句是在`return` 之后执行的，其实不然，实际上`finally` 里的语句是在`return` 之前执行的。那么问题来了，既然是在之前执行，那为什么`a` 的值没有被覆盖了？
实际过程是这样的：当程序执行到try{}语句中的return方法时，它会干这么一件事，将要返回的结果存储到一个临时栈中，然后程序不会立即返回，而是去执行finally{}中的程序，在执行`a = 2`时，程序仅仅是覆盖了a的值，但不会去更新临时栈中的那个要返回的值  。执行完之后，就会通知主程序“finally的程序执行完毕，可以请求返回了”，这时，就会将临时栈中的值取出来返回。这下应该清楚了，要返回的值是保存至临时栈中的。
再来看一个例子,稍微改下上面的程序：

```java
 public abstract class Test {     
     public static void main(String[] args) {         
         System.out.println(beforeFinally());     
     }          
     public static int beforeFinally(){         
         int a = 0;         
         try{             
             a = 1;             
             return a;         
         }finally{             
             a = 2;             
             return a;         
         }     
     } 
 } 
/**output: 2 */
```

 在这里，finally{}里也有一个return，那么在执行这个return时，就会**更新临时栈中的值**。同样，在执行完finally之后，就会通知主程序请求返回了，即将临时栈中的值取出来返回。故返回值是2. 

[trycatch处理的两种方式](https://www.bilibili.com/video/BV1Cv411372m?p=135&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

自定义异常

<table><tr>
    <td><img src=Javase.assets/1716557643638.png></td>
    <td><img src=Javase.assets/1716557674791.png></td>
</tr></table>

**Throwable中的常用方法：**

- `public void printStackTrace()`
- `public String getMessage()`

**Error：**例如：StackOverflowError（栈内存溢出）和OutOfMemoryError（堆内存溢出，简称OOM）。

<img src=Javase.assets/1716557251478.png width=80% align=left>

手动抛出异常对象：throw

Java 中异常对象的生成有两种方式：

- 由虚拟机**自动生成**：程序运行过程中，虚拟机检测到程序发生了问题，那么针对当前代码，就会在后台自动创建一个对应异常类的实例对象并抛出。
- 由开发人员**手动创建**：`new 异常类型([实参列表]);`，如果创建好的异常对象不抛出对程序没有任何影响，和创建一个普通对象一样，但是一旦throw抛出，就会对程序运行产生影响了。

5.1 使用格式

```java
throw new 异常类名(参数);
```

5.2 使用注意点

throw语句会导致程序执行流程被改变，throw语句是明确抛出一个异常对象，因此它`下面的代码将不会执行`。

如果当前方法没有try...catch处理这个异常对象，throw语句就会`代替return语句`提前终止当前方法的执行，并返回一个异常对象给调用者。

```java
package com.atguigu.keyword;

public class TestThrow {
    public static void main(String[] args) {
        try {
            System.out.println(max(4,2,31,1));
        } catch (Exception e) {
            e.printStackTrace();
        }
        try {
            System.out.println(max(4));
        } catch (Exception e) {
            e.printStackTrace();
        }
        try {
            System.out.println(max());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public static int max(int... nums){
        if(nums == null || nums.length==0){
            throw new IllegalArgumentException("没有传入任何整数，无法获取最大值");
        }
        int max = nums[0];
        for (int i = 1; i < nums.length; i++) {
            if(nums[i] > max){
                max = nums[i];
            }
        }
        return max;
    }
}

```

# 常用的类与API

接下来要讲的类与API呢，都是非常常用的，直接看API文档或者源码，根本看不懂一点，因此，这里的建议是跟着学，以及上网搜具体用法。

## String类

String类的实例化(即创建对象)的方式有两种，一种是直接赋值，一种是构造器。构造方法有很多，这里介绍几个。

```java
String s1 = "hello,world"; 
String s2 = new String("hello,world");
String s3 = new String();           //空串
String s4 = new String(new char[]{'a','b','c'});     // abc
String s5 = new String(new byte[]{97,98,99});        // abc
```

```java

String s = "hello,world";
//public int length():返回字符串的字符个数
System.out.println(s.length());
//public char charAt(int index):获取下标为index的字符
char c = s.charAt(0);
System.out.println(c);
// 遍历字符串
for(int i = 0; i < s.length(); i++){
    char c1 = s.charAt(i);
    System.out.print(c1);
}
System.out.println();
//public char[] toCharArray():将字符串转成字符数组
char[] charArray = s.toCharArray();

//遍历字符数组
for(int i = 0; i < charArray.length; i++){
    System.out.print(charArray[i]);
}
```

```java
String s1 = new String("Hello World");
String s2 = new String("Hello World");
System.out.println(s1 == s2); //false,这是两个独立的对象，地址不同
System.out.println(s1.equals(s2)); // true,字符串内容一致
System.out.println(Objects.equals(s1, s2));// true
```

```java
String s1 = "34AeFG";
String s2 = "34aEfg";
// public boolean equalsIgnoreCase(String anotherString):忽略大小写比较内容
System.out.println(s1.equalsIgnoreCase(s2));//true

//public String substring(int beginIndex, int endIndex):截取[begin,end)子串
System.out.println(s1.substring(0, 5));//34AeF

//public String substring(int beginIndex):截取[begin,最后]的子串
System.out.println(s1.substring(5));//G

String s = "这是个垃圾电影，这个电影真垃圾";
//public String replace(CharSequence target, CharSequence replacement)
System.out.println(s.replace("垃圾", "**"));//这是个**电影，这个电影真**

//public boolean contains(CharSequence s)
System.out.println(s.contains("垃圾"));//true

//public boolean startsWith(String prefix):判断是否是以字符串prefix开头
System.out.println(s.startsWith("这是")); // true

String s3 = "张无忌,周芷若,赵敏,殷素素";
//public String[] split(String regex):按照字符串regex分割，各个元素放入String数组中
String[] split = s3.split(",");
System.out.println(Arrays.toString(split)); //[张无忌, 周芷若, 赵敏, 殷素素]
```



字符串常量池

> 什么是常量？
>
> 在程序运行过程中，其值不能被改变的量称为常量。例如，字面值就是一种常量，被final修饰的也是一种常量。

String类是我们平常项目中使用频率非常高的一种类型，jvm为了提升性能和减少内存开销，避免字符串的重复创建，其维护了一块特殊的内存空间，即字符串常量池。

JVM会为字符串字面值在常量池中创建对象。

1. 执行`String s1= "hello";`后，JVM在常量池中创建一个字符串为`hello`的String类对象,并让s1指向该对象
2. 执行`String s2= "hello";`时，JVM会先检查常量池中是否存在字符串为`hello`的String类对象，如果存在就直接让s2指向该空间，否则就会在常量池中开辟一个新的空间存放该字符串，并让s2指向该对象。

```java
String s1 = "hello";
String s2 = "hello";
System.out.println(s1 == s2);  // true
//由打印得到true可知，这俩指向的是同一个String类对象，即在字符串常量池中创建的那个对象。
```

面试题：

```java
String s1 = new String("hello");  
String s2 = "hello";
```

> 第一行代码创建了两个对象，根据字面值"hello"在常量池创建String对象，再new一个String对象在堆空间。
>
> 第二行代码没有创建对象，因为"hello"在常量池已存在，会直接引用常量池的对象。

```java
String s1 = "abc";
String s2 = "a" + "b" + "c";  //编译器会直接将结果算出来。因为这仨都是常量,所以s2="abc";
System.out.println(s1==s2); //true
```

```java
String s1 = "abc";
String s2 = "ab";
String s3 = s2 + "c"; //底层是new的对象赋给了s3
System.out.println(s1 == s3); // false
```



## StringBuilder、StringBuffer

因为String对象是不可变对象，虽然可以共享常量对象，但是对于字符串的频繁修改和拼接操作，效率极低，空间消耗也比较高。因此，JDK又在java.lang包提供了可变字符序列StringBuffer和StringBuilder类型。

> StringBuilder是线程不安全的，StringBuffer是线程安全的

```java
// 调用空参构造器
StringBuilder sb1 = new StringBuilder();   // 换成StringBuffer是一样的
// public StringBuilder(String str)
StringBuilder sb2 = new StringBuilder("hello,world");
// public StringBuilder append(各种类型 i):向字符串尾部追加
sb2.append(12);
sb2.append("yeah");   // s2="hello,world12yeah"
// 链式编程:看源码返回的是this指针
sb1.append("hello").append(" world"); // s1 = hello world
// public int length()
System.out.println(sb1.length());  // 11
// public StringBuilder reverse(): 原地翻转字符串
System.out.println(sb1.reverse()); // dlrow olleh
// public String toString():StringBuilder--->String
String string = sb1.toString();
System.out.println(string);  //dlrow olleh
```

你去看看StringBuilder的API文档，都是些增删改查的方法。而String的API文档都是一些转换成其他类型的方法，增删改查的方法很少。

> 对字符串操作建议使用StringBuilder或StringBuffer，不要使用String
>
> String类也可以实现增删改查，但操作效率极低，原因是因为对String类对象进行增删改查时都要创建新对象，而不是原地操作。[Java基础常见面试题总结(中) | JavaGuide](https://javaguide.cn/java/basis/java-basic-questions-02.html#字符串拼接用-还是-stringbuilder)

StringJoiner格式化字符串

```java
StringJoiner sj1 = new StringJoiner(",");
sj1.add("张无忌").add("赵敏").add("殷素素").add("灭绝师太");
System.out.println(sj1);        // 张无忌,赵敏,殷素素,灭绝师太
System.out.println(sj1.length());   // 15
String string = sj1.toString();  //StringJoiner---->String
StringJoiner sj2 = new StringJoiner(",","[","]");
sj2.add("张无忌").add("赵敏").add("殷素素").add("灭绝师太");
System.out.println(sj2);      // [张无忌,赵敏,殷素素,灭绝师太]
```

## Math、System

```java
//public static int abs(int a):取绝对值
System.out.println(Math.abs(-1));   // 1
//public static double ceil(double a):向上取整
System.out.println(Math.ceil(3.14)); // 4.0
//public static double floor(double a):向下取整
System.out.println(Math.floor(3.14));//3.0
//public static long round(double a):四舍五入
System.out.println(Math.round(3.45)); // 3
//public static double max(double a, double b)
System.out.println(Math.max(3, 4.2)); // 4.2
//public static double min(double a, double b)
System.out.println(Math.min(3, 4.2)); //3.0
//public static double pow(double a, double b)
System.out.println(Math.pow(2, 4));  //16.0
//public static double random():从[0,1)中取随机数
System.out.println(Math.random()); //0.8554160649604127
```

```java
//public static native long currentTimeMillis():返回1970-1-1 0:0:0到此刻的毫秒值
System.out.println(System.currentTimeMillis());
//public static void exit(int status):status非0表示异常终止JVM
System.exit(0);  //status=0表示人为终止JVM
```



## BigDecimal

用于解决浮点数计算结果失真的问题

```java
System.out.println(0.1+0.2); //0.30000000000000004
```

```java
double a1 = 0.1, a2 = 0.2;
//public BigDecimal(double val):不要使用这个构造器
//BigDecimal b1 = new BigDecimal(a1);
//public BigDecimal(String val):使用String为入参的构造器
BigDecimal b1 = new BigDecimal(String.valueOf(a1));
BigDecimal b2 = new BigDecimal(Double.toString(a2));
//public BigDecimal add(BigDecimal augend):Returns a BigDecimal whose value is (this + augend)
BigDecimal b3 = b1.add(b2);
System.out.println(b3);  //0.3
```

```java
BigDecimal b3 = b1.add(b2); //加  0.3
BigDecimal b4 = b2.subtract(b1); //减 0.1
BigDecimal b5 = b1.multiply(b2); //乘 0.02
BigDecimal b6 = b1.divide(b2, 2, BigDecimal.ROUND_HALF_UP); //除 0.50
// 2表示保留两位小数，  BigDecimal.ROUND_HALF_UP:四舍五入
```

```java
//public double doubleValue():将BigDecimal对象转为double
double v = b1.doubleValue();
```

流程就是将double转为BigDecimal，用BigDecimal进行运算，最后再转为double。

## JDK8之前：日期时间API

Date类

```java
//调用无参构造器:获取系统当前的时间
Date d = new Date();
System.out.println(d);  //Sun May 26 20:53:06 CST 2024
//public long getTime():获取January 1, 1970, 00:00:00到该对象存储的时间的毫秒值
System.out.println(d.getTime());  //1716728031330
//public Date(long date):获取January 1, 1970, 00:00:00+毫秒值date的Date对象
Date d2 = new Date(d.getTime()+1000);
System.out.println(d2);   //Sun May 26 20:54:55 CST 2024A
```

返回当前系统的时间，再根据getTime()获取毫秒值，再在毫秒值的基础上加减，就可以表示其他时间了。下面是一个例子，这种太麻烦了。接下来会介绍Calendar会简单点。

<img src=javase.assets/1716730104875.png width=40% align =left>

SimpleDateFormat类

```java
//调用无参构造器:获取系统当前的时间
Date d = new Date();
System.out.println(d);   //Sun May 26 21:25:04 CST 2024
//public SimpleDateFormat(String pattern)
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
//public final String format(Date date)
String format = sdf.format(d);
System.out.println(format);   //2024-05-26 21:25:04

String s = "2024-05-26 21:21:27";
//public Date parse(String source):将字符串解析成Date对象
Date parse = sdf.parse(s);
System.out.println(parse);   //Sun May 26 21:21:27 CST 2024
```

Calendar类

```java
// 获得封装当前日历的Calendar对象
Calendar calendar = Calendar.getInstance();
// public int get(int field): 去API文档可以看到Calendar所有的field
System.out.println(calendar.get(Calendar.YEAR)); //2024
System.out.println(calendar.get(Calendar.MONTH));//4
System.out.println(calendar.get(Calendar.DAY_OF_MONTH));//26
//public final Date getTime():获得Date对象
Date time = calendar.getTime();
//public long getTimeInMillis():获取毫秒值
long timeInMillis = calendar.getTimeInMillis();
//public void set(int field, int value)
calendar.set(Calendar.DAY_OF_MONTH, 1);
System.out.println(calendar.get(Calendar.DAY_OF_MONTH)); //1
calendar.add(Calendar.DAY_OF_MONTH, -1);
System.out.println(calendar.get(Calendar.DAY_OF_MONTH));//30
```

## JDK8：新的日期时间API

<img src=javase.assets/1716732681295.png width=50% align =left>

TODO







## 正则表达式

[03、正则表达式：概述、初体验、匹配规则_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Cv411372m?p=132&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

[Pattern (Java SE 17 & JDK 17) (oracle.com)](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/regex/Pattern.html)

\d 说明是digit数字 匹配一个数字字符。等价于 [0-9]。

\w说明是word单词 匹配字母、数字、下划线。等价于'[A-Za-z0-9_]'。



