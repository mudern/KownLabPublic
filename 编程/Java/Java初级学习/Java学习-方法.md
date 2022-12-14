 Java学习-方法

标签（空格分隔）： #Java

---

# 方法定义
方法，是语句的集合，组合执行功能。
1.方法是解决一类问题的**步骤**的有序组合
2.方法**包含于类或对象中**
3.方法在**程序中被创建**，在其他地方**被引用**
# 方法优点：
1.程序简短清晰
2.利于程序维护
3.提高开发效率
4.提高重用性
# 方法命名规则：
1.第一个单词开头小写，后面单词开头大写，遵循[[程序编写规范-命名规范]]
2.下划线出现于测试方法中用以分隔名称的逻辑组件
# [[方法结构]]
一般情况下，定义一个方法包含一下语法：

    修饰符 返回值类型 方法名(参数类型 参数名){
        ...
        方法体
        ...
        return 返回值;
    }
1.修饰符：修饰符可选，用于告诉编译器如何调用方法，定义方法访问类型。
2.返回值类型：方法可能返回值，returnValueType是返回值的数据类型。可以不返回，仅执行一定操作，如果返回值，可将该值保存在变量中，没有返回值时，returnValueType的关键字为void。
3.方法名：方法的实际名称，方法名和参数表共同构成方法签名。
4.参数类型：参数像是占位符，当方法被调用，传递值给参数，这个值被称为实参或变量。参数列表是指方法的类型，顺序和参数的个数，参数时可选的，方法可以不包含任何参数。
5.方法体：方法体包含具体语句，定义该方法的功能。

**方法包含方法头和方法体**

# 方法调用
Java支持两种调用方法的方式，根据方法是否返回值来选择。当程序调用一个方法时，程序控制权将被移交给被调用的方法。当被调用的方法的返回语句执行或到达方法闭括号时候，将控制权交还给程序。当方法返回一个值的时候，方法调用通常被当作一个值。
如果方法的返回值为void，方法调用一定为语句。

# 方法[[重载]]
重载指一个类的两个方法拥有**相同的名字**作为重载的依据，但是有**不同的参数列表**作为选择不同方法的依据。
在输入不同类型数据时，具体调用的方法可以略有不同。
Java编译器根据方法签名[^methodsignature]判断哪个方法应该被调用。
方法重载可以让程序更加清晰易读。执行密切相关任务的方法应使用相同名字。重载方法必须拥有不同的参数列表，不能仅仅根据修饰符或者返回类型不同来重载方法。

# [[变量作用域]]
变量的范围时程序中变量可以被引用的部分。
方法内定义的变量被成为局部变量。局部变量的作用范围从声明开始，直到包含他的块结束。局部变量必须声明才可以使用。
方法的参数范围涵盖整个方法，参数实际上是一个局部变量，for循环的初始化部分声明变量，其作用范围在整个循环。
但循环体内声明的变量其适用范围是从它声明到循环体结束。
可以在同一方法内，不同的非嵌套块中多次声明一个具有相同名称的变量，但不能在嵌套块中两次声明相同名称局部变量。

# 命令行参数
如果希望一个程序运行时再传递相应消息，需要依靠传递命令行参数给main（）函数实现。命令行参数是在执行程序时紧跟在程序名字后面的信息。
以主程序为例：

    class A {
        public static void main(String args[]) {
    
        for (int i = 0; i < args.length; i++)
                System.out.println(args[i]);
    
        }
    }
Java程序入口是[[main方法]]，main方法可以接受一个命令行参数，其为一个String[]数组。命令行参数有JVM接受用户输入并传给main方法。
编译命令：  javac A.java
执行命令： java A a b c d f
那么在执行命令后，将遍历输出所输入字符

#[[编程/Java/Java基础概念/构造函数]]]
当一个对象被创建的时候，构造方法用来初始化该对象。构造方法和它所在类的名字相同，但构造方法**没有返回值**。
通常会使用构造方法给一个类的**实例变量赋初值**，或者**执行其他必要的步骤**来**创建一个完整的对象**。


# 可变参数
Java支持传递同类型的可变参数给一个方法，声明如下：

    typeName... parameterName

在方法声明中，在指定参数类型后加一个省略号。一个方法中只能指定一个可变参数，他必须是方法的最后一个参数。任何普通的参数必须在他之前声明。

# finalize方法
Java允许定义这样的方法，他在对象被垃圾回收器析构（回收）之前调用，这个方法叫做finalize（），他用来清除回收对象。
可以使用finalize（）来确保一个对象打开的文件被关闭了。在finalize()方法里，你必须指定在对象销毁时候要执行的操作。finalize（）一般格式是：

    protected void finalize()
    {
       // 在这里终结代码
    }

关键字protected是一个限定符，他确保finalize（）方法不会被该类以外的代码调用。Java的内存可以由JVM来自动完成，如果你手动使用，则可以使用上面的方法。


[^methodsignature]:[[方法签名]]是用来区分不同方法的标识符。Java中的方法必须依赖于类，方法是由方法名，形参列表，返回值以及方法体构成的。由于重载方法之间方法名相同，那么就势必要从构成方法的其他要素中找到另一要素与方法名能构成唯一表示的方法签名，即需使用形参列表和返回值。对于调用方法的人来说，方法的形参数据列表的重要类型远高于返回值，所以方法有方法名和形参列表组成。方法名和形参数据类型列表可以唯一确定一个方法，是判断重载的重要依据。

