# Linux学习笔记-Linux的启动过程


标签（空格分隔）： #Linux
---

## Linux的启动过程 ##

 1. 内核引导
 2. 运行init初始程序
 3. 系统初始化
 4. 建立终端
 5. 用户登录

>init程序类型
>SysV:init 适用于CentOS 5及以前版本 配置文件位置：/etc/inittab
>Upstart:init 适用于CentoS 6版本 配置文件位置：/etc/inittab或/etc/init/*/conf
>Systemd:systemd 适用于CentOS7 配置文件位置：/usr/lib/systemd/system或/etc/systemd/system

### 内核引导
 1. 计算机接通电源启动
 2. Bios开机自检
 3. 按照Bios设置读取硬盘
 4. 操作系统接管硬件
 5. 读取/boot 目录下内核文件

### init程序内部运行
运行init程序引发其他程序
首先读取配置文件
> 配置文件位置：/etc/inittab

**运行级别：**
init程序任务之一为引发一系列开机启动程序——守护进程（daemon）
守护进程根据具体的需求类别不同有所不同
Linux为不同场合分配不同开机启动程序，叫做运行级别（runlevel）即根据运行级别来确定的运行程序

**Liunx的7个运行级别**
0：系统停机状态，默认运行级别不能为0，否则无法正常启动
1：单用户状态，root权限，用于系统维护，禁止远程登录
2:非完全多用户状态（无NFS[^NFS]）
3:完全多用户状态（有NFS）登录后进入控制台命令行模式
4:系统未使用，保留给用户
5:图形模式[^Graphics mode]
6:系统重启[^System restart]


### 系统初始化
init配置文件中的

    si::sysinit:/etc/rc.d/rc.sysinit

其调用执行了/etc/rc.d/rc.sysinit
其本身为bash shell脚本，作用为完成系统的初始化
各个运行级别都将首先运行

> **系统初始化内容：**
1.激活交换分区
2.检查磁盘
3.加载硬件模块
4.其他需要优先执行的任务

    l5:5:wait:/etc/rc.d/rc 5[^5]
此行代码以为以5作为参数运行shell脚本，将会执行/etc/rc.d/rc5.d/目录下所有rc启动脚本，这些启动脚本都为连接文件，不是真正脚本。真正脚本在/etc/rc.d/init.d/目录下
rc脚本[^rc]具有类似用法，常见参数有start，stop，restart，status
/etc/rc.d/rc5.d/中启动脚本通常是以K或S[^KS]开头+特定运行等级的数字[^num]的连接文件，对于以S开头启动脚本，将以start参数运行
如果发现存在相应脚本存在K开头连接，且处于运行态，[^symbol]则将首先以start为参数停止以开始运行的守护进程，然后再重新运行。
目的是保证init改变运行级别时，所有相关守护进程将重启。
用户可以通过chkconfig或setup中的"System Services"来自行设定每个运行级中运行哪些守护进程。

### 建立终端
rc运行脚本执行完毕，返回init。此时基本环境已初始化完成，守护进程相应启动。
init程序此时会打开6个终端，以便用户登录系统。
inittab中的6行代码对应了6个终端

> 
1:2345:respawn:/sbin/mingetty tty1
2:2345:respawn:/sbin/mingetty tty2
3:2345:respawn:/sbin/mingetty tty3
4:2345:respawn:/sbin/mingetty tty4
5:2345:respawn:/sbin/mingetty tty5
6:2345:respawn:/sbin/mingetty tty6[^tty]

其中数字对应相应的运行等级，不存在数字0，0等级时对应系统停机，系统无法正常启动。

从以上代码可以看出各运行级别中都将以respawn方式运行mingetty程序，此程序能打开终端，设置模式。
同时它将显示文本登录界面，即常见登录界面，此界面会提示用户输入用户名，用户输入的内容将作为参数传递给login程序，即登录程序验证用户身份。


### 用户登录系统
用户登录存在3种常见方式

 1. 命令行登录
 2. ssh登录[^ssh]
 3. 图形界面登录

运行级别为5的图形方式用户将通过图形化登录界面登录，登录成功后可以直接进入KDE，Gnome等窗口管理器。
Liunx账号验证程序为login
login会接收mingetty传来的用户名作为用户名参数。
然后login将会对用户名进行分析，如果用户名不为root，且存在/etc/nologin文件，login将输出nologin文件内容并退出。
这通常用来系统维护时防止非root用户登录。只有在/etc/securetty中登记的终端才允许root用户登录，如果不存在这个文件，则root用户可以在任何终端上登录。
/etc/usertty文件用于对用户做出附加访问限制，如果不存在这个文件，则无其他额外限制。

**图形模式与文字模式的切换**

Liunx预设6个命令，窗口终端用于登录。
默认登录窗口为1，即tty1。
如果已经安装图形界面，默认进入图形界面
可以按下Ctrl + Alt + F1 ~ F6进行切换。
如果使用VMware虚拟机，命令窗口切换的快捷键为Alt + Space + F1~F6，如果在图形界面则为Alt + Shift + Ctrl + F1~F6切换至命令窗口。

**Liunx关机**
正确关机流程：sync > shutdown > reboot > halt
关机指令：shutdown
shutdown命令基本信息如下：

 - 命令名称：shutdown
 - 英文含义：bring the system down
 - 所在路径：/sbin/shutdown
 - 执行权限：sbin
 - 功能描述：关机于重启

**命令格式**
 > [root@localhost ~]# shutdown [选项] 时间 [警告信息]

**选项**
c：取消已经执行的 shutdown 命令；
h：关机；
r：重启；

**其他相关命令**
reboot用于执行重启操作
> [root@localhost ~]# reboot
>重启


halt与poweroff用于执行关机操作
> [root@localhost ~】# halt
>关机
>[root@localhost ~】# poweroff
>关机

init通过修改Liunx运行级别实现关机与重启操作

> [root@localhost~]# init 0
关机，也就是调用系统的 0 级别
[root@localhost ~】# init 6
重启，也就是调用系统的 6 级别

无论是重启或是关闭系统，首先需要运行sync命令，将内存数据写入磁盘。

命令实例:
> sync 将数据由内存同步到硬盘中。

>shutdown 关机指令，你可以man 

>shutdown 来看一下帮助文档。

>例如你可以运行如下命令关机：

>shutdown –h 10 ‘This server will 

>shutdown after 10 mins’ 

>这个命令告诉大家，计算机将在10分钟
后关机，并且会显示在登陆用户的当前屏幕中。

>shutdown –h now 立马关机

>shutdown –h 20:25 
系统会在今天20:25关机

>shutdown –h +10 十分钟后关机

>shutdown –r now 系统立马重启

>shutdown –r +10 系统十分钟后重启
reboot 就是重启，等同于 shutdown –r now

>halt 关闭系统，等同于shutdown –h now 和 poweroff

[^NFS]:网络文件系统，Sun公司研制的Unix表示层协议，能够使使用者访问网络文件。

[^Graphics mode]:X11控制台，登陆后进入图形GUI模式。

[^System restart]:默认运行级别不能设为6，否则不能正常启动

[^5]:此处参数意为运行等级

[^rc]:rc为run commands运行命令缩写

[^KS]:K意为kill，S意为Start，D意为disable

[^num]:即运行等级，当出现多个时，将先执行数字较小的脚本，再以较小数字对应的运行等级的身份运行接下来的脚本

[^symbol]:以/var/lock/subsys/下的文件作为标志

[^ssh]:ssh为Secure Shell  Protocol安全外壳协议缩写，是一种加密网络传输协议，ssh通过在网络间建立安全隧道来实现ssh客户端与服务器之间的连接，其最常见的用途是远程登录系统，利用ssh来传输命令行界面与远程执行命令。其通过非对称加密实现身份验证。

[^tty]:tty为Teletypewriter或Teleprinter的缩写，普遍用于任何类型计算机终端或虚拟控制台。

