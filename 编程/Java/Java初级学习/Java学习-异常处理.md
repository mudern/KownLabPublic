# Java学习-异常处理

标签（空格分隔）： #Java

---

### [[Java异常]] ###
Java程序中的异常：
1.用户输入非法数据
2.要打开文件不存在
3.网络中断或JVM溢出

基本可以分为用户错误引起，程序错误引起，物理错误引起。

- 检查性异常：用户错误或问题引发的异常，无法被预见。
- 运行时异常：可以预见避免，编译时可被忽略。
- 错误：非异常，脱离控制。常被忽略，编译无法检查。

### [[Exception类]]的层次 ###
异常类都是java.lang.Exception类继承的子类。
Exception类时Throwable的子类，Throwable还有子类Error。
Error用来只是运行环境时发生的错误。
Java程序通常不捕获错误。错误发生在严重故障中，在Java程序处理范围之外。
Error用来指示运行时环境发生的错误。
Java内置类中有大部分常用[[检查性异常]]和[[非检查性异常]]。

### Java内置异常类 ###
异常类在java.lang标准包中。
标准运行时异常类的子类是最常见的异常类。由于java.lang包是默认加载到所有的Java程序的，所以大部分从运行时异常类的继承而来的异常都可以直接使用。
Java根据各个类库也定义了一些其他的异常，包括检查性异常和非检查性异常

### [[捕获异常]] ###
使用try和catch关键字可以捕获异常。可以放在异常可能发生的地方，此代码块内的代码被称为保护代码。

    try
    {
       // 程序代码
    }catch(ExceptionName e1)
    {
       //Catch 块
    }
    
Catch语句包含要捕获异常类型的声明。当保护代码块中发生一个异常时，try后面的catch块就会被检查。
如果异常包含在catch块中，异常会被传递到该catch块，这和传递一个参数到方法时一样的。

### [[多重捕获块]] ###
一个try代码块后面跟随多个catch代码块的情况叫做多重捕获。

    try{
       // 程序代码
    }catch(异常类型1 异常的变量名1){
      // 程序代码
    }catch(异常类型2 异常的变量名2){
      // 程序代码
    }catch(异常类型3 异常的变量名3){
      // 程序代码
    }

### [[throws&throw关键字]] ###
如果一个方法没有捕获到一个检查性异常，那么该方法必须使用throws关键字来声明。throws关键字放在方法签名尾部。
也可以使用throw关键字抛出一个异常，无论是新实例化还是刚刚捕获到的。
一个方法可以声明抛出多个异常，多个异常之间用逗号隔开。

    import java.io.*;
    public class className
    {
       public void withdraw(double amount) throws RemoteException,
                                  InsufficientFundsException
       {
           // Method implementation
       }
       //Remainder of class definition
    }
    
### [[finally关键字]] ###
finally关键字用来创建try代码块后面执行的代码块。
无论是否发生异常，finally代码块中的代码总会被执行。
在finally代码块中，可以运行善后性质语句。
finally代码块出现在catch代码块最后。

    try{
      // 程序代码
    }catch(异常类型1 异常的变量名1){
      // 程序代码
    }catch(异常类型2 异常的变量名2){
      // 程序代码
    }finally{
      // 程序代码
    }
    
    
注意事项：
 - catch不能独立与try存在
 - 在try/catch后面添加finally块并非强制要求
 - try代码后不能既没有catch也没有finally
 - try，catch，finally块间不能添加任何代码

    






  [1]: https://www.runoob.com/wp-content/uploads/2013/12/exception-hierarchy.png