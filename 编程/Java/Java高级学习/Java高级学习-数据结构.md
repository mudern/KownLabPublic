# Java高阶学习-数据结构

标签（空格分隔）： #Java #Index 

---

Java数据结构中主要接口与类：
传统框架：

 - 枚举(Enumeration)
 - 位集合(BitSet)
 - 向量(Vector)
 - 栈(Stack)
 - 字典(Dictionary)
 - 哈希表(Hashtable)
 - 属性(Properties)

新型框架：

 - 集合框架(Collection)
 
## [[枚举]] ##
枚举接口定义了一种从数据结构中取回连续元素的方式。
枚举定义了nextElement方法，由于得到包含多元素数据结构下一个元素。

## [[位集合]] ##
位集合实现了一组可以单独设置和清除的位和标志。
该类在处理一组布尔值时有用，只需给每个值赋值一位，然后对位进行适当设置清除。

## [[向量]] ##
向量与传统数字十分类似，但大小可以根据需要动态变化。
与数组一样，向量的元素可以通过索引访问。
优点在于创建对象时不必指定对象大小，大小根据需要动态变化。

## [[栈]] ##
栈实现了后进先出的数据结构。
每添加一个元素时，元素将被放在顶部。
每取出一个元素时，将从栈顶取出元素。
最后进栈的元素先被取出。

## [[字典]] ##
字典类为抽象类，定义了KV类数据结构，由键映射到值(keyvalue)。
想要通过特定的键，而非整数索引来访问数据时，应该使用字典。
由于字典类是抽象类，只提供了键映射到值的数据结构，没有具体实现。

## [[哈希表]] ##
哈希表类提供了用户定义键结构基础上组织数据的手段。
哈希表键的具体含义取决于使用场景和包含数据。

## [[属性]] ##
属性类继承于哈希表属性类，表示了一个持久的属性集，属性列表中的每个键对应值都是一个字符串。
属性类被多中Java基础类调用。
