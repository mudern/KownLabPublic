# Java学习-String类与StringBuffer & StringBuilder类 


标签（空格分隔）： #Java

---
## [[String类]] ##
### 字符串创建###
一般两种创建字符串的方法：
1.String str=""
2.String str=new Str("")
String类不可改变，创建String后，其值无法改变，如果需要对其做较多更改，应选择StringBuffer & StringBuilder 类。
### 字符串长度###
用于获取有关对象的信息的方法称为访问器方法。
String 类的一个访问器方法是length()方法，它返回字符串对象包含的字符数。 
### 连接字符串###
一般两种连接字符串方法：
1.string1.concat(string2);
2.string1+string2
### 创建格式化字符串###
我们知道输出格式化数字可以使用 printf() 和 format() 方法。
String 类使用静态方法 format() **返回一个String 对象而不是 PrintStream 对象。**
String 类的静态方法 format() 能用来**创建可复用的格式化字符串**，而不仅仅是用于一次打印输出。
### String方法 ###
|SN(序号)|方法描述|
|-----|-----|------|
|1|char charAt(int index)|返回指定索引处的 char 值。|
|2|int compareTo(Objecto)|把这个字符串和另一个对象比较。|
|3|int compareTo(StringanotherString)|按字典顺序比较两个字符串。|
|4|int compareToIgnoreCase(Stringstr)|按字典顺序比较两个字符串，不考虑大小写。|
|5|String concat(Stringstr)|将指定字符串连接到此字符串的结尾。|
|6|boolean contentEquals(StringBuffersb)|当且仅当字符串与指定的StringBuffer有相同顺序的字符时候返回真。|
|7|static StringcopyValueOf(char[]data)|返回指定数组中表示该字符序列的 String。|
|8|static String copyValueOf(char[] data, int offset, intcount)|返回指定数组中表示该字符序列的 String。|
|9|boolean endsWith(Stringsuffix)|测试此字符串是否以指定的后缀结束。|
|10|boolean equals(ObjectanObject)|将此字符串与指定的对象比较。|
|11|boolean equalsIgnoreCase(StringanotherString)|将此 String 与另一个 String 比较，不考虑大小写。|
|12|byte[] getBytes()|使用平台的默认字符集将此 String 编码为byte序列，并将结果存储到一个新的 byte 数组中。|
|13|byte[] getBytes(StringcharsetName)|使用指定的字符集将此String编码为byte序列，并将结果存储到一个新的 byte 数组中。|
|14|void getChars(int srcBegin, int srcEnd, char[] dst, intdstBegin)|将字符从此字符串复制到目标字符数组。|
|15|int hashCode()|返回此字符串的哈希码。|
|16|int indexOf(intch)|返回指定字符在此字符串中第一次出现处的索引。|
|17|int indexOf(intch,intfromIndex)|返回在此字符串中第一次出现指定字符处的索引，从指定的索引开始搜索。|
|18|int indexOf(Stringstr)|返回指定子字符串在此字符串中第一次出现处的索引。|
|19|int indexOf(Stringstr,int)|返回指定子字符串在此字符串中第一次出现处的索引，从指定的索引开始。|
|20|String intern()|返回字符串对象的规范化表示形式。|
|21|int lastIndexOf(intch)|返回指定字符在此字符串中最后一次出现处的索引。|
|22|int lastIndexOf(int ch, int fromIndex)|返回指定字符在此字符串中最后一次出现处的索引，从指定的索引处开始进行反向搜索。|
|23|int lastIndexOf(Stringstr)|返回指定子符串在此字符串中最右边出现处的索引|。
|24|int lastIndexOf(Stringstr,intfromIndex)|返回指定子字符串在此字符串中最后一次出现处的索引，从指定的索引开始反向搜索。|
|25|int length()|返回此字符串的长度。|
|26|booleanmatches(Stringregex)|告知此字符串是否匹配给定的正则表达式。|
|27|boolean regionMatches(boolean ignoreCase, int toffset, String other, intooffset,intlen)|测试两个字符串区域是否相等|。
|28|boolean regionMatches(int toffset, String other, int ooffset, int len)|测试两个字符串区域是否相等。|
|29|String replace(charoldChar,charnewChar)|返回一个新的字符串，它是通过用 newChar 替换此字符串中出现的所有 oldChar 得到的。|
|30|String replaceAll(Stringregex,Stringreplacement)|使用给定的 replacement 替换此字符串所有匹配给定的正则表达式的子字符串。|
|31|String replaceFirst(Stringregex,Stringreplacement)使用给定的 replacement|替换此字符串匹配给定的正则表达式的第一个子字符串。
|32|String[] split(Stringregex)|根据给定正则表达式的匹配拆分此字符串。|
|33|String[]split(Stringregex,intlimit)|根据匹配给定的正则表达式来拆分此字符串。|
|34|boolean startsWith(Stringprefix)|测试此字符串是否以指定的前缀开始。|
|35|boolean startsWith(Stringprefix,inttoffset)|测试此字符串从指定索引开始的子字符串是否以指定前缀开始。|
|36|CharSequencesubSequence(intbeginIndex,intendIndex)|返回一个新的字符序列，它是此序列的一个子序列。|
|37|String substring(intbeginIndex)|返回一个新的字符串，它是此字符串的一个子字符串。|
|38|String substring(intbeginIndex,intendIndex)|返回一个新字符串，它是此字符串的一个子字符串。|
|39|char[] toCharArray()|将此字符串转换为一个新的字符数组。
|40|String toLowerCase()|使用默认语言环境的规则将此 String 中的所有字符都转换为小写。
|41|String toLowerCase(Locale locale)|使用给定 Locale 的规则将此 String 中的所有字符都转换为小写。
|42|String toString()|返回此对象本身（它已经是一个字符串！）。
|43|String toUpperCase()|使用默认语言环境的规则将此 String 中的所有字符都转换为大写。
|44|String toUpperCase(Locale locale)|使用给定 Locale 的规则将此 String 中的所有字符都转换为大写。
|45|String trim()|返回字符串的副本，忽略前导空白和尾部空白。
|46|static String valueOf(primitive data type x)|返回给定data type类型x参数的字符串表示形式。
|47|contains(CharSequence chars)|判断是否包含指定的字符系列。
|48|isEmpty()|判断字符串是否为空。

### [[StringBuffer & StringBuilder类]] ###
对字符串的修改操作，需要使用StringBuffer & StringBuilder类，与string类不同，StringBuffer & StringBuilder类的对象能被多次修改，且不产生新的未使用对象。
在使用StringBuffer类时，每次都会对StingBuffer对象本身进行操作，且不生成新的对象，所以如果需要对字符串进行修改，应使用StringBuffer。
StringBuilder类与StringBuffer类不同在于其本身不是线程安全的（不能被同步访问），但其本身具有速度优势，所以一般情况建议使用StringBuilder类。
#### StringBuffer 方法 ####
以下是 StringBuffer 类支持的主要方法：
|序号|方法|描述|
|-----|-----|-----|
|1|public StringBufferappend(Strings)|将指定的字符串追加到此字符序列。|
|2|public StringBuffer reverse()|将此字符序列用其反转形式取代。|
|3|public delete(int_start,int_end)|移除此序列的子字符串中的字符。|
|4|public insert(int offset, int i)|将 int 参数的字符串表示形式插入此序列中。|
|5|insert(int offset, String str)|将 str 参数的字符串插入此序列中。|
|6|replace(int start, int end, String str)|使用给定 String 中的字符替换此序列的子字符串中的字符。
|1|int capacity()|返回当前容量。|
|2|char charAt(int index)|返回此序列中指定索引处的 char 值。|
|3|void ensureCapacity(int minimumCapacity)|确保容量至少等于指定的最小值。|
|4|void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)|将字符从此序列复制到目标字符数组 dst。|
|5|int indexOf(String str)|返回第一次出现的指定子字符串在该字符串中的索引。|
|6|int indexOf(String str, int fromIndex)|从指定的索引处开始，返回第一次出现的指定子字符串在该字符串中的索引。|
|7|int lastIndexOf(String str)|返回最右边出现的指定子字符串在此字符串中的索引。|
|8|int lastIndexOf(String str, int fromIndex)|返回 String 对象中子字符串最后出现的位置。|
|9|int length()|返回长度（字符数）。|
|10|void setCharAt(int index, char ch)|将给定索引处的字符设置为 ch。|
|11|void setLength(int newLength)|设置字符序列的长度。|
|12|CharSequence subSequence(int start, int end)|返回一个新的字符序列，该字符序列是此序列的子序列。|
|13|String substring(int start)|返回一个新的 String，它包含此字符序列当前所包含的字符子序列。|
|14|String substring(int start, int end)|返回一个新的 String，它包含此序列当前所包含的字符子序列。|
|15|String toString()|返回此序列中数据的字符串表示形式。|



