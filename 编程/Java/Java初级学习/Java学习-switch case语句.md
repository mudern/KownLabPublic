# Java学习-switch case语句

标签（空格分隔）： #Java

---

[[switch case]] 语句判断一个变量与一系列值中某个值是否相等，每个值称为一个分支。

语法：

    switch(expression){
        case value :
           //语句
           break; //可选
        case value :
           //语句
           break; //可选
        //你可以有任意数量的case语句
        default : //可选
           //语句
    }

语法规则：

- switch 语句中的变量类型可以是： **byte、short、int 或者 char**。从 Java SE 7 开始，switch支持字符串 String 类型了，同时case标签必须为**字符串常量或字面量**。 switch 语句可以拥有多个 case 语句。
- 每个case后面跟一个要比较的值和冒号。
- case 语句中的值的数据类型必须与变量的数据类型相同，而且只能是常量或者字面常量。 当变量的值与case 语句的值相等时，那么 case 语句之后的语句开始执行，直到 break 语句出现才会跳出 switch 语句。
- 当遇到break语句时，switch语句终止。程序跳转到switch语句后面的语句执行。case 语句不必须要包含break语句。如果没有 break语句出现，程序会继续执行下一条 case 语句，直到出现 break 语句。
- switch 语句可以包含一个default 分支，该分支一般是switch语句的最后一个分支（可以在任何位置，但**建议在最后一个**）。default在没有case语句的值和变量值相等的时候执行。default 分支不需要 break 语句。
- 如果 case 语句块中没有 break 语句时，JVM 并不会顺序输出每一个 case 对应的返回值，而是继续匹配，匹配不成功则返回默认 case。
- 如果 case语句块中没有break语句时，匹配成功后，从当前case开始，后续所有case的值都会输出。如果后续的case语句块有break语句则会跳出判断。

