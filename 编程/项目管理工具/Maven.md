#Maven #项目管理工具
https://www.liaoxuefeng.com/wiki/1252599548343744/1309301146648610
---

在Java项目中一般使用Maven作为项目管理工具
```ascii
a-maven-project
├── pom.xml
├── src
│   ├── main
│   │   ├── java
│   │   └── resources
│   └── test
│       ├── java
│       └── resources
└── target
```
在其中,project是项目名,pom.xml是项目描述,src是soureces简写,存放着测试和实际代码,target存放打包好的项目文件.在src文件夹中,main是项目主体,test是测试文件夹;java存放源码,resources存放项目所需资源文件.

下面介绍pom.xml项目描述.
```xml
<project ...>
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.itranswarp.learnjava</groupId>
	<artifactId>hello</artifactId>
	<version>1.0</version>
	<packaging>jar</packaging>
	<properties>
        ...
	</properties>
	<dependencies>
        <dependency>
            <groupId>commons-logging</groupId>
            <artifactId>commons-logging</artifactId>
            <version>1.2</version>
        </dependency>
	</dependencies>
</project>
```
在其中,modelVersion是模型版本.
groupId是类似包名,一般为组织和公司名称,artifactId是Java类名,一般为项目名,version是项目版本,由这三个量,可唯一确定一个Maven项目.在引用其他第三方库时也遵守相同的三个量确定一个类.
dependencies是依赖,第三方库,在声明第三方库后,Maven会自动下载并把其放入classpath.
