# Java学习-正则表达式

标签（空格分隔）： #Java

---
正则用于搜索编辑处理文本，Java中正则表达式的描述与其他语言基本一致。
此笔记主要介绍Java正则相关的包与方法。
## 类 ##
java.util.regex 包主要包括以下三个类：
> Pattern 类： pattern 对象是一个正则表达式的编译表示。Pattern 类没有公共构造方法。要创建一个Pattern对象，你必须首先调用其**公共静态编译方法**，它返回一个**Pattern**对象。该方法**接受一个正则表达式作为它的第一个参数**。 
Matcher 类：
Matcher对象是对输入字符串**进行解释和匹配操作的引擎**。与Pattern类一样，Matcher 也**没有公共构造方法[^PublicConstructor]**。你需要调用Pattern 对象的matcher 方法来获得一个 Matcher 对象。
PatternSyntaxException：
PatternSyntaxException 是一个**非强制异常类**，它表示一个正则表达式模式中的语法错误。
##捕获组##

捕获组是把多个字符当一个单独单元进行处理的方法，它通过对括号内的字符分组来创建。
捕获组是通过从左至右计算其开括号来编号。例如，在表达式（（A）（B（C））），有四个这样的组：

    ((A)(B(C)))
    (A)
    (B(C))
    (C)

可以通过调用 matcher 对象的 groupCount 方法来查看表达式有多少个分组。groupCount 方法返回一个 int 值，表示matcher对象当前有多个捕获组。
还有一个特殊的组（group(0)），它总是代表整个表达式。该组不包括在 groupCount 的返回值中。 

### [[Matcher类]] ###
## 索引方法 ##
索引方法提供了有用的索引值，精确表明输入字符串所能找到匹配的位置。
public int start()
返回以前匹配的初始索引
public int start(int group)
返回在以前的匹配操作期间，由给定组所捕获的子序列的初始索引。
public int end()
返回最后匹配字符之后的偏移量。
public int end(int group)
返回在以前的匹配操作期间，由给定组所捕获子序列的最后字符之后的偏移量。
## 查找方法 ##
查找方法用来检查输入的字符串并返回一个布尔值，表示是否找到该模式，多用于条件判断语句的条件判断。
pubulic boolean lookingAt()
尝试将从区域开头开始的输入序列与该模式匹配。
public boolean find()
尝试查找与该冒失匹配的输入序列的下一个子序列。
public boolean find(int start)
重置此匹配器，然后尝试查找匹配该模式，从指定索引开始的输入序列的下一个子序列。
public boolean matches()
尝试将整个区域与模式匹配。
## 替换方法 ##
替换方法是替换输入字符串里文本的方法：
public Matcher appendReplacement(StringBuffer sb,String replacement)
实现非终端添加和替换步骤。
public StringBuffer appendTail(StringBuffer sb)
实现终端添加和替换步骤。
public String replaceAll(String replacement)
替换模式与给定替换字符串相匹配的输入序列的每个子序列。
public String replaceFirst(String replacement)
替换模式与给定替换字符串匹配的输入序列的第一个子序列。
public static String quoteReplacement(String s)
返回指定字符串的字面替换字符串。这种方法返回一个字符串，就像传递给Matcher类的appendReplacement方法一个字面字符串一样工作。




[^PublicConstructor]:应指公共构造函数[[编程/Java/Java基础概念/构造函数]]]即指构造函数时被调用的方法，公共即指公用，否则无法被调用。

