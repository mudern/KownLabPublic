#Java 

---

# 优点
静态工厂方法用来获取类实例,静态工厂方法相比于构造器对于整个类进行实例化.可以控制实例化范围.有以下优点.
1. 减少内存分配开销.控制获得类实例的具体路径,防止不必要的内存开销.
2. 在访问单一的实例时,有命名的构造器减少了调用难度.[[编程/杂项/构造函数|构造函数]]名称不够灵活.
3. 可以使用相应的子类.静态工厂类可以返回器子类.
**总结**:静态工厂类的最大优势就是增大类的提供者对自己所提供类的控制力.

# 实例

以下代码在用户不知道构造器填入参数的情况下,实现了实例的构建.

```Java
public class Factory {

    private static final String Apple = "apple";

    private static final String Pineapple = "pineapple";
	
    private String name;

  

    public Factory(String name){

        this.name = name;

    }

    public static Factory setApple() {

        return new Factory(Apple);

    }

    public static Factory setPineapple(){

        return new Factory(Pineapple);

    }

  

    public static void main(String[] args) {

        var a = Factory.setApple();

        System.out.println(a.name);

        var b = Factory.setPineapple();

        System.out.println(b.name);

    }
}
```