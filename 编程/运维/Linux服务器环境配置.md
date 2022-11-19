#Linux 

---
# 下载Java
Oracle官网下载对应版本JDK,linux-x86版本.用ftp协议传输到服务器.

# 服务器端


## JDK布设
1. 压缩文件放置在/usr/local
2. 对tar归档文件进行解压
```shell
tar -xvf [filename]
```

## etc文件修改
修改环境变量并使之生效.
环境变量文件位置:/etc/profile
使用vim打开
```shell
vim /etc/profile
```
编辑文件profile
```
#set java environment
JAVA_HOME=/usr/local/jdk1.8
CLASS_PATH=.:$JAVA_HOME/lib/
PATH=$PATH:$JAVA_HOME/bin
export JAVA_HOME CLASS_PATH PATH

```
## etc文件生效
```shell
source /etc/profile
```
## 检查Java安装情况
```shell
java -version
\\检查java
javac -version
\\检查javac
\\确定两版本对应一致,防止服务器已经预装了jre
```