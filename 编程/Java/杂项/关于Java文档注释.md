#Java 

---
Java中存在自动文档注释Javadoc,可以用其生成高水准文档.
Javadoc会抽取的信息包括:
 - 模块
 - 包
 - 公共接口和类
 - 公共和受保护的字段
 - 公共和受保护的构造器和方法

注释基本结构:
```Java
/**
content
**/
```
# 通用注释
通用注释用以表示通用性的内容.
@since text:引入关于此版本特性的任何描述
@auther:作者信息
@version:版本信息,版本描述
@see:使用超链接,可以使用包,类,方法及变量名(使用#分隔类和方法),使用<herf = >字符,则需指定一个网络位置,使用"",文本则会显示在see also部分.
@link:任意插入一个标记,与see类似
@index entry:建立一个索引(Java9后适用)

# 类注释
import语句后,类语句前.描述类的作用.

# 方法注释
@param variable  意为parament,即变量,对变量进行描述
@return 对returns进行描述
@throws 表明有可能抛出异常

# 字段注释
对公共字段进行建立文档.

# 包注释
要在包文件中添加一个单独文件.
1. 可以名为package-info.java必须包含注释和package语句,且不包含其他
2. 提供名为package.html文件,会抽取\<body>...\</body>

# 抽取注释

