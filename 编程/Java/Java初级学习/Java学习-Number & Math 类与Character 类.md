# Java学习-Number & Math 类与Character 类

标签（空格分隔）： #Java

---

Number & Math 类
---------------

### [[Number类]] ###
**Number类主要包含常用内置数据类型：**
整数类型：
byte：1个字节，8位，256种状态，取值范围为[－128,127]
short:2个字节，16位，65536种状态，取值范围为[-32768,32767]
int:4个字节，32位，整数类型默认是int类型，取值范围约21亿
long:8个字节，64位，long类型表示long类型常量，要加L或者l，建议加L
浮点类型：
float:4个字节，32位，单精度，能精确到6~7位，声明一个小数类型，要加F或者f，建议加F
double:8个字节，64位，双精度，能精确到15~16位，小数类型默认是double类型
布尔类型
boolean：占1位，有true和false2个值，一个表示真，一个表示假，一般用于表示逻辑运算。
### [[Math类]] ###
**Math类主要包含常用数学计算**，Math方法被定义为static格式，通过Math可在主函数内调用。

> 1.xxxValue() 将 Number 对象转换为xxx数据类型的值并返回。 
2.compareTo()将number对象与参数比较。
3.equals() 判断number对象是否与参数相等。
4. 	valueOf()返回一个Number对象指定的内置数据类型。
5.toString() 以字符串形式返回值。
6.parseInt()将字符串解析为int类型。
7.abs() 返回参数的绝对值。
**8.ceil() 返回大于等于(>=)给定参数的的最小整数，类型为双精度浮点型。
9.floor() 返回小于等于（<=）给定参数的最大整数。**
10.rint()返回与参数最接近的整数。返回类型为double。
**11.round() 它表示四舍五入，算法为Math.floor(x+0.5)，即将原来的数字加上0.5后再向下取整，所以，Math.round(11.5)的结果为12，Math.round(-11.5) 的结果为-11。**
12.min() 返回两个参数中的最小值。
13.max()返回两个参数中的最大值。
14.exp() 返回自然数底数e的参数次方。
15.log() 返回参数的自然数底数的对数值。
16.pow() 返回第一个参数的第二个参数次方。
17.sqrt() 求参数的算术平方根。
18.sin()求指定double类型参数的正弦值。
19.cos() 求指定double类型参数的余弦值。
20.tan()求指定double类型参数的正切值。
21.asin() 求指定double类型参数的反正弦值。 22.acos()求指定double类型参数的反余弦值。
23.atan() 求指定double类型参数的反正切值。 24.atan2()将笛卡尔坐标转换为极坐标，并返回极坐标的角度值。
25.toDegrees() 将参数转化为角度。
26.toRadians()将角度转换为弧度。
**27.random() 返回一个随机数。**

### [[Character类]] ###
Character 类用于对单个字符进行操作。
Character 类在对象中包装一个基本类型 char 的值
在某些情况下，Java编译器会自动创建一个Character对象。
将一个char类型的参数传递给**需要一个Character类型参数的方法时，那么编译器会自动地将char类型参数转换为Character对象**。 这种特征称为装箱，反过来称为拆箱。 
#### 转义序列####
前面有反斜杠（\）的字符代表转义字符，它对编译器来说是有特殊含义的。 
|转义序列|描述|
|:------|:------|
|\t|在文中该处插入一个tab键|
|\b|在文中该处插入一个后退键|
|\n|在文中该处换行|
|\r|在文中该处插入回车|
|\f|在文中该处插入换页符|
|\'|在文中该处插入单引号|
|\"|在文中该处插入双引号|
|\\\ |在文中该处插入反斜杠|
#### Character方法####
|序号|方法|描述|
|-----|-----|-----|
|1|isLetter()|是否是一个字母|
|2|isDigit()|是否是一个数字字符|
|3|isWhitespace()|是否是一个空白字符
|4|isUpperCase()|是否是大写字母|
|5|isLowerCase()|是否是小写字母|
|6|toUpperCase()|指定字母的大写形式|
|7|toLowerCase()|指定字母的小写形式|
|8|toString()|返回字符的字符串形式，字符串的长度仅为1|

### [[String类]] ###
两种一般创建字符串的方法：
1.String str=""
2.String str=new Str("")
String类不可改变，创建String后，其值无法改变，如果需要对其做较多更改，应选择StringBuffer & StringBuilder 类。





