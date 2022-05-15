



为什么 数据类型负数多一位存储

为什么0.1无法在浮点数中精确，0.5可以

记得添加主函数，否则无法调用方法。

使用三元运算符，里面所有的类型都要一致！



eclipse中三个双引号可以自动换行加字符串



printf可以指定格式输出



前面讲过了浮点数在计算机中常常无法精确表示，并且计算可能出现误差，因此，判断浮点数相等用`==`判断不靠谱：例如if语句中。



Q：为什么String创建的两个引用类型，值一样是相等的



eclipse 格式化 ctrl+shift+f，我的电脑这个快捷键也是切换繁简。。



`for each`循环无法指定遍历顺序，也无法获取数组的索引。for(i:n)，则i代表具体数据的值



JUnit 中 覆盖部分代码为黄色



任何`class`的构造方法，第一行语句必须是调用父类的构造方法。如果没有明确地调用父类的构造方法，编译器会帮我们自动加一句`super();`



但是，`Person`类并没有无参数的构造方法，因此，编译失败。



向上向下转型意义



java 转型问题其实并不复杂，只要记住一句话：父类引用指向子类对象。子类和父类中定义同名的变量时，仅仅是隐藏了，变量没有多态性；而对于覆盖的方法，Java表现出多态性，会调用更具体的子类里面的方法，无论从哪里调用，无论使用什么引用类型调用。



 注意：方法名相同，方法参数相同，但方法返回值不同，也是不同的方法。在Java程序中，出现这种情况，编译器会报错。



不理解：

答案还是不行，因为去掉父类的`run()`方法，就失去了多态的特性。例如，`runTwice()`就无法编译：

```
public void runTwice(Person p) {
    p.run(); // Person没有run()方法，会导致编译错误
    p.run();
}
```



* 面向抽象的编程，为什么尽量引用上层，如Person s = new Student();

* question 

在使用的时候，实例化的对象永远只能是某个具体的子类，但总是通过接口去引用它，因为接口比抽象类更抽象：

```
List list = new ArrayList(); // 用List接口引用具体子类的实例
Collection coll = list; // 向上转型为Collection接口
Iterable it = coll; // 向上转型为Iterable接口
```



为什么静态方法类似其它编程语言的函数。



因为静态方法属于`class`而不属于实例，因此，静态方法内部，无法访问`this`变量，也无法访问实例字段，它只能访问静态字段。



为什么:

静态方法经常用于工具类。例如：

- Arrays.sort()
- Math.random()

静态方法也经常用于辅助方法。注意到Java程序的入口`main()`也是静态方法。







`interface`是可以有静态字段的，并且静态字段必须为`final`类型???





**当同一个包下有两个以上的包时，Eclipse才会以树状显示包结构**。



未解决：https://www.liaoxuefeng.com/wiki/1252599548343744/1260467032946976

第一种，直接写出完整类名，例如：

```
// Person.java
package ming;

public class Person {
    public void run() {
        mr.jun.Arrays arrays = new mr.jun.Arrays();
    }
}
```

包没有父子关系，`com.apache`和`com.apache.abc`是不同的包。



实验不理解：

由于Java支持嵌套类，如果一个类内部还定义了嵌套类，那么，嵌套类拥有访问`private`的权限：

https://www.liaoxuefeng.com/wiki/1252599548343744/1260466215676512





不理解：

### Anonymous Class

还有一种定义Inner Class的方法，它不需要在Outer Class中明确地定义这个Class，而是在方法内部，通过匿名类（Anonymous Class）来定义。示例代码如下：

https://www.liaoxuefeng.com/wiki/1252599548343744/1376414781669409



实践Jar包



一个`.java`文件只能包含一个`public`类，为什么？



这是因为通过`new String(char[])`创建新的`String`实例时，它并不会直接引用传入的`char[]`数组，而是会复制一份，所以，修改外部的`char[]`数组不会影响`String`实例内部的`char[]`数组，因为这是两个不同的数组。

从`String`的不变性设计可以看出，如果传入的对象有可能改变，我们需要复制而不是直接引用。





idea:ctrl+alt+l 自动对齐



时刻记得main函数，遇到奇怪问题先排查这个





为什么不推荐使用

```
Integer n1 = new Integer(100);
```







仔细观察结果的童鞋可以发现，`==`比较，较小的两个相同的`Integer`返回`true`，较大的两个相同的`Integer`返回`false`，这是因为`Integer`是不变类，编译器把`Integer x = 127;`自动变为`Integer x = Integer.valueOf(127);`，为了节省内存，`Integer.valueOf()`对于较小的数，始终返回相同的实例

以上，为什么





```
//为防止enum顺序被改变，可以如下定义
enum WeekdayEnumIndex{
    MON(1),TUE(2),WED(3),THU(4),FRI(5),SAT(6),SUN(0);

    public final int dayValue;

    private WeekdayEnumIndex(int dayValue){
        this.dayValue = dayValue;
    }
}
```

以上的括号语法如何成立







```
BigDecimal d1 = new BigDecimal("123.4500");
BigDecimal d2 = d1.stripTrailingZeros();
System.out.println(d1.scale()); // 4
System.out.println(d2.scale()); // 2,因为去掉了00

BigDecimal d3 = new BigDecimal("1234500");
BigDecimal d4 = d3.stripTrailingZeros();
System.out.println(d3.scale()); // 0
System.out.println(d4.scale()); // -2
```

如果一个`BigDecimal`的`scale()`返回负数，例如，`-2`，表示这个数是个整数，并且末尾有2个0。



为什么是-2？



















JAVA项目的jdk升级/降级https://blog.csdn.net/aha_xigua/article/details/115870783











练习https://www.liaoxuefeng.com/wiki/1252599548343744/1255938912141568需要深入理解