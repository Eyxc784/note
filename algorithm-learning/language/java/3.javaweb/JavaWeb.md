JavaWeb

JavaBean

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

### 单例模式

(Singleton)

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
> 在程序运行过程中，其值**不能**被改变的量称为常量。例如，字面值就是一种常量，被final修饰的也是一种常量。

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



```java
String s1 = "coder";     
String s2 = "coder";     
String s3 = "coder" + s2;     
String s4 = "coder" + "coder";     
String s5 = s1 + s2;            
System.out.println(s3 == s4);  //false
System.out.println(s3 == s5);    //false
System.out.println(s4 == "codercoder");//true
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

## BigInteger

在 Java 中，有许多数字处理的类，比如 Integer类，但是Integer类有一定的局限性。

我们都知道 Integer 是 Int 的包装类，int 的最大值为 2^31-1。若希望描述更大的整数数据时，使用Integer 数据类型就无法实现了，所以Java中提供了BigInteger 类。

BigInteger类型的数字范围较Integer，Long类型的数字范围要大得多，它支持任意精度的整数，也就是说在运算中 BigInteger 类型可以准确地表示任何大小的整数值而不会丢失任何信息。

```

```



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

\d 是数字的意思，\D是非数字的意思    