#C

---
enum枚举多用于C中的一种基本数据类型.最大的作用是限制输出输出的范围,同时还可以提高提高代码可读性.

# 语法
```C
enum　枚举名　{枚举元素1,枚举元素2,……};
```


# 定义
枚举变量存在三种常用方式定义
1. ***先*定义枚举类型，*再*定义枚举变量**
```C
enum DAY
{
      MON=1, TUE, WED, THU, FRI, SAT, SUN
};
enum DAY day;
```

2. **定义枚举类型的*同时*定义枚举变量**
```C
enum DAY
{
      MON=1, TUE, WED, THU, FRI, SAT, SUN
} day;
```

3. ***省略*枚举名称，*直接*定义枚举变量*
```C
enum
{
      MON=1, TUE, WED, THU, FRI, SAT, SUN
} day;
```

# 枚举变量实质
枚举变量实质上是int,