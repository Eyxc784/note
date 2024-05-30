JAVA权限修饰符解析

java权限修饰符有四种：private、public、默认、protected



我们分成两级介绍：

高一级：类和接口

低一级：类和接口的成员



先介绍类和接口：

类和接口的权限修饰符有两个：public、默认

public：所有包的所有类和接口可见。

默认：本包内的所有类和接口可见。

对于类和接口来说，可见性意味着可以声明。



接下来介绍 接口的成员：

接口的成员的修饰符有两个：public、private

public：所有包所有类和接口可见

private：只有本接口可见



对于成员来说，可见意味着可以访问。



访问成员的方式本质上只有一种，即通过`变量名.成员名`访问。本质上还是用的this访问。

this、super的访问路径：就近往上找原则。



接下来介绍类的成员：

类的成员有成员变量、成员方法、构造器、代码块、内部类。

其中代码块不能被权限修饰符修饰。



类的成员的权限修饰符：private、public、默认、protected

对于成员的可见性，指的是可访问。

private：本类内可见

public：所有包的所有类和接口可见

默认：本包内可见。

protected：

在父类内定义一个protected成员，**在父类所在的包内**，无论是定义父类对象、与父类同一个包下的子类对象，还是不同包下的子类对象，都可以访问protected成员。即保持默认权限。除此之外，**在其他包的子类内**，只有子类对象能访问protected成员。









举个例子：

```java
package a;

public class Father {
    protected int i;
}

public class Son1 extends Father{}

package b;
import a.Father;
public class Son2 extends Father{}
```

在a包里定义了一个父类Father及其子类Son1

在b包里定义了一个父类Father的子类Son2

父类Father中有一个protected成员变量`i`



接下来我们在以下几个地方创建父类Father的对象，并通过该对象访问protected成员。观察规律。

本类、本包的子类、本包的非子类、其他包的子类、其他包的非子类





```java
package a;

public class Father {     //在本类内创建父类Father对象并访问protected成员。
    protected int i;
    
    Father f = new Father();
    {
        System.out.print(f.i);   //没有编译错误，说明可以访问。
    }
}
```



```java
package a;

public class Son1 extends Father{   //在本包的子类内创建父类Father对象并访问protected成员。
    Father f = new Father();
    {
        System.out.println(f.i);    //没有编译错误，说明可以访问。
    }
}
```



```java
package a;

public class Main{       //在本包的非子类内创建父类Father对象并访问protected成员。
    public static void main(String[] args){ 
        Father f = new Father();
        System.out.println(f.i);   //没有编译错误，说明可以访问。
    }
}
```



```java
package b;

import a.Father;

public class Son2 extends Father {  //在其他包的子类内创建父类Father对象并访问protected成员。
    Father f = new Father();
    {
        System.out.println(f.i);  // 编译出错，说明不能访问。
    }
}
```



```java
package b;


import a.Father;

public class Main{  //在其他包的非子类内创建父类Father对象并访问protected成员。
    public static void main(String[] args) {
        Father f = new Father();
        System.out.println(f.i);   //  编译出错，说明不能访问。
    }
}
```



总结：创建父类对象访问protected成员，在本类、本包的子类、本包的非子类 可以访问，即在本包内可以访问。在其他包的子类、其他包的非子类 不能访问， 即在其他包内不可以访问。这不就相当于默认权限吗？

总结：通过父类对象访问protected成员，相当于访问默认成员。包内可见（package-private）





接下来我们创建与父类Father同一个包下的子类Son1的对象，并通过该对象访问protected成员。观察规律。

通过敲代码可知，创建与父类同一个包下的子类对象访问protected成员，也不能跨包。本质与上面是一样的。



创建与父类不是同一个包下的子类对象访问protected成员，**在父类所在的包内可以访问**。**在该子类内也可以访问**

这一点还是和默认权限有差别的，因为默认权限是不能跨包的。

总结：

在父类内定义一个protected成员，**在父类所在的包内**，无论是定义父类对象、与父类同一个包下的子类对象，还是不同包下的子类对象，都可以访问protected成员。即保持默认权限。除此之外，**在其他包的子类内**，只有子类对象能访问protected成员。



本质上，继承就是向上搜索机制。

封装是把各种成员集成在一起，另一方面就是提供可见性。

**我们的权限修饰符既实现了封装，也实现继承。**









