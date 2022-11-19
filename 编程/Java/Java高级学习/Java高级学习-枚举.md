# Java高级学习-枚举

标签（空格分隔）： #Java

---

枚举类是特殊类，一般表示一组常量。枚举类使用enum关键字定义，常量用逗号","来分割。
### 内部类中使用枚举###
枚举类可以声明在内部类中。
每个枚举都是通过Class在内部实现，枚举值都是public static final的。
### 迭代枚举元素###
for语句迭代枚举元素：
```Java
    public static void main(String[] args){
        for (Enum x : Enum.values()){
            System.out.println(x);
        }
    }

```
### 在switch中使用枚举类###

```Java
    enum Enum{
    1,2,3
    }
    public class A{
        public static void main(String[] args){
        switch(x){
            case 1:
                break;
            case 2:
                break;
            case 3:
                break;
            }
        }
    }
    
```

### enum类的values()，ordinal()，valueOf()方法###
enum类实现了Serializable和Comparable两个接口。

 - values()方法返回枚举类中的所有值。
 - ordinal()方法可以找到每个枚举变量的索引，类比数组。
 - valueOf()方法返回指定字符串值的枚举常量。
 
### 枚举类成员###
枚举和不同类一样可以使用自己的变量，方法和构造函数，构造函数只能使用private访问修饰符，外部无法调用。
枚举可以包含具体方法，也可以包含抽象方法，如果枚举类有抽象方法，每个枚举类的实例必须对其加以实现。


