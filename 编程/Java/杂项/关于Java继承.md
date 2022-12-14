#Java 

---
# [[Java高级学习-继承|继承]]定义
Java继承,可以基于已有的类创建新的类,继承已经存在的类,就是在复用该类的方法.
类和子类应该为is-a的关系,即本质上是.子类也是父类,以说他是(is-a)父类,虽然他和父类有所不同.

# [[关键字|关键字]]
Java继承使用extends关键字.使用[[super]]表示调用父类方法.

# [[重载]]
对于子类与父类的区别,可以相同的方法名有不同处理方法的,可以使用override[[重载]]方法,这样,在不同的类中,可以有不同的具体实现.

# [[编程/Java/Java基础概念/构造函数|构造器]]
子类调用父类构造器super(a,b,c).必须写在首行.
子类如果没有显式调用父类构造器,那么将自动调用父类[[编程/Java/Java基础概念/构造函数|无参构造器]],如果父类没有无参构造器,且未调用父类其他构造器,那么编译器将报错.
在创建子类实例时,不会创建与之对应的父类实例,其创建只是调用了父类的构造方法,在内存中,依然是属于子类的数据.

# 继承要求
子类对于方法访问的限制应该与父类保持一致或严于父类.