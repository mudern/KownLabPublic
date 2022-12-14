# Java高级学习-继承

标签（空格分隔）： #Java

---

# 继承：
子类继承父类特征行为，是子类对象具有父类的实例域和方法，或子类从父类继承方法，使得子类具有父类相同行为。

# 继承关键字：
extends，implements
所有类继承于java.lang.Object，当一个类没有继承的两个关键字，则默认继承object。
## extends关键字
类的继承是单一继承，一个子类拥有一个父类，extends只能继承一个类。
## implements关键字
使用implements关键字可以变相的使Java具有多继承的特性，使用范围为类继承接口的情况，可以同时继承多个接口。
## [[super]]关键字
可以通过对super关键字来实现对父类成员的访问，用来引用当前对象的父类。
## [[this]]关键字
实现对自身对象的访问，指向自己的引用。
## [[final]]关键字
final可以用来修饰变量(包括类属性，对象属性，局部变量和形参)，方法(包括类方法和对象方法)和类。
final关键字将类定义为最终类，不能被继承，或者用于修饰方法，该方法不能被子类重写。

关于**this**关键字：
1.全局变量与局部变量重名时，使用this指向局部变量
this.x/super.x
2.让类中的方法，访问该类中另一个方法或实例变量
this.fun
3.this()用于[[编程/Java/Java基础概念/构造函数]]]](不能在普通方法中使用，只能写在构造方法中)
public X(){
    this()
}
关于**super**关键字：
1.super可以指向父类的实例变量

    super.x

2.super可以调用父类的方法

    super.fun()

3.super可以调用父类的构造函数

    public classx(a,b){
        super(a,b)
    }
