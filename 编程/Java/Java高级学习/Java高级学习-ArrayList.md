# Java高级学习-ArrayList

标签（空格分隔）： #Java

---

ArrayList类是一个可以动态修改的数组，无固定大小限制，可以增添删除元素。其继承了AbstractList，实现了List接口。

![ https://www.runoob.com/wp-content/uploads/2020/06/ArrayList-1-768x406-1.png]

引用ArrayList语法：

    import java.util.ArrayList; // 引入 ArrayList 类
    
    ArrayList<E> objectName =new ArrayList<>();　 // 初始化

E：泛型数据类型，用于设置objectName数据类型，只能引用为数据类型
objectName:对象名

### 添加元素###

ArrayList类提供众多方法，添加元素可以使用add()方法，其中括号写入添加内容。

### 访问元素###
访问元素可以使用get()方法，其中括号写入元素索引值，从零开始。

  
  