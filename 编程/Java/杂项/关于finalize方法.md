#Java

---
在Java中可以使用构造函数进行类的实例化,这部分内存开销,JVM会通过GC机制进行回收.
但是对于非new产生的特殊内存,JVM将不会进行回收,所以需要手动对这部分内存进行回收,这时就需要使用finalize方法.而finalize方法必须用于垃圾回收之前.所以不建议使用finalize方法处理对象,因为finalize方法的调用时机不确定,也不能保证确实被调用,且运行代价高昂,无法保证调用顺序.此方法只会在系统GC机制清理内存时处理特殊内存.所以只建议在处理本地对象(JNI创建)或者释放非内存资源(socket,文件)时使用.
```Java
protected void finalize(){  
// finalization code here  
}
```
