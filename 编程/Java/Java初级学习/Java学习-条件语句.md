﻿Java学习-条件语句

标签（空格分隔）： #Java

---

# [[if]]语句
if 语句的语法如下：

    if(布尔表达式) {    
    //如果布尔表达式为true将执行的语句 }

如果布尔表达式的值为 true，
则执行 if 语句中的代码块，
否则执行 if 语句块后面的代码。 

# [[if...else]]语句
if 语句后面可以跟 else 语句，当 if 语句的布尔表达式值为 false 时，else 语句块会被执行。
语法：
if…else 的用法如下：

    if(布尔表达式){
       //如果布尔表达式的值为true
    }else{
       //如果布尔表达式的值为false
    }

# [[if...else if...else]]语句

if 语句后面可以跟 else if…else 语句，这种语句可以检测到多种可能的情况。

使用 if，else if，else 语句的时候，需要注意下面几点：
1.if 语句至多有 1 个 else 语句，else 语句在所有的 else if 语句之后。
2.if 语句可以有若干个 else if 语句，它们必须在 else 语句之前。
3.一旦其中一个 else if 语句检测为 true，其他的 else if 以及 else 语句都将跳过执行。
语法：

    if...else 语法格式如下:
    if(布尔表达式 1){
       //如果布尔表达式 1的值为true执行代码
    }else if(布尔表达式 2){
       //如果布尔表达式 2的值为true执行代码
    }else if(布尔表达式 3){
       //如果布尔表达式 3的值为true执行代码
    }else {
       //如果以上布尔表达式都不为true执行代码
    }




