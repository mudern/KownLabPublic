Java高级学习-集合框架

标签（空格分隔）： #Java 

---
集合框架的设计满足一下目标：

 - 框架本身高性能，基本集合实现高性能
 - 框架允许不同类型集合以类似方式工作，具有高度互操作性
 - 集合便于扩展适应
 
整个集合框架围绕标准接口设计。可以直接使用接口标准实现。

集合主要包含两种类型容器：
1.集合(Collection)
用与储存一个元素集合。
2.图(Map)
用于存储键值对映射。

集合下有List，Set，Queue子类型，ArrayList，LinkedList，HashSet，LinkedHashSet，HashMap，LinkedHashMap具体实现类。
集合框架用于代表和操作集合的统一架构。所有集合框架包含以下内容：

 - 接口：代表集合的抽象数据类型。定义多个接口，便于多态操作集合对象。
 - 实现(类)：集合接口具体实现。可以重复使用的数据结构。
 - 算法：实现集合接口的对象里的方法执行计算（搜索排序）。这些算法被称为多态，相同的方法可以在相似的接口上有不同的实现。
 
除集合外，框架同时定义了Map接口和类。Map里存储的是键值对。尽管Map不是集合，但是其完全整合在集合中。

## [[集合接口]] ##

### Collection ###
最基本的集合接口。一个Collection代表一组Object，即Collection元素，Java不提供直接继承自Collection的类，只提供继承于的子接口。
Collection接口存储一组不唯一，无序的对象。

### List ###
List接口是有序的Collection。使用此接口能够精确控制每个元素插入位置，能够通过索引来访问List中元素。
List接口存储一组不唯一，有序插入顺序的对象。

### Set ###
Set接口具有与Collection完全一致的接口，只是行为上不同，Set不保存重复的元素。
Set接口存储一组唯一无序对象。

### SortedSet ###
继承于Set保存有序的集合。

### Map ###
Map接口存储一组键值对象，提供键值映射。

### Map.Entry ###
描述Map中的一个元素，键值对。是一个Map的内部接口。

### SortedMap ###
继承于Map，使Key保持在升序排列。

### Enumeration ###
传统的接口和定义方法，通过它可以枚举对象集合中的元素。其本身已被迭代器取代。

#### Set和List区别 ####

 - Set接口实例存储无序不重复。List接口实例存储有序可重复。
 - Set检索效率低，删除插入效率高，插入删除不会引起元素位置改变。
 - List检索效率高，删除插入效率低，插入删除会引起元素位置改变。与数组类似，可以动态增长，根据实际存储数据长度自动增长List长度。

## [[集合实现类]] ##
Java提供一套实现Collection接口的标准集合类。包含抽象类和具体类。

### Vector ###
与ArrayList类似，该类是同步的，可以在多线程中使用，允许设置默认增长长度，默认扩容方式为原来两倍。

### Stack ###
Stack是Vector的子类，实现了标准先进先出的栈。

### Dictionary ###
Dictionary类是抽象类，用来存储键值对，作用与Map类类似。

### Hashtable ###
Hashtable是Dictionary的子类。

### Properties ###
Properties继承于Hashtable，表示持久属性集，属性列表每个键及其对应值都是一个字符串。

### BitSet ###
一个BitSet类创建一种特殊类型的数组来保存位值。BitSet中数组大小会根据需要增加。

## [[集合算法]] ##
集合框架定义多种算法，用于集合与映射。这些算法被定义为集合类的静态方法。
在尝试比较不兼容类型时，一些方法能够抛出ClassCastException异常。
在试图修改一个不可修改的集合时，抛出UnsupportedOperationException异常。
集合定义了三个静态变量：EMPTY_SET，EMPTY_LIST，EMPTY_MAP。这些变量都不可改变。

## 迭代器使用##
遍历集合元素。
一般遍历数组都是采用for循环或者增强for，这两个方法可以用于集合框架。
另一种方法时采用迭代器遍历集合框架，它是一种对象，实现了lterator或Listlerator接口。
迭代器能够使你通过循环来得到或删除集合元素。Listlterator继承了lterator，以允许双向遍历列表和修改元素。

## 比较器使用 ##
TreeSet和TreeMap按照排序顺序来存储元素。这是通过比较器来精确定义按照特定顺序排序。
Java Comparator接口可以让我们以不同的方式来排序一个集合。

## 总结##
Java集合框架提供了预先包装的数据结构和算法用于操纵。
集合时一个对象，可容纳其他对象引用。集合接口声明对每一种类型的集合可以执行的操作。
任何对象加入集合类后，自动转变为Object类型，(所有的类都属于Object类，这里属于一个拆箱过程)取出时，需要进行强制类型转换(这里属于一个装箱过程)。


 










