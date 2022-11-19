#Git #项目管理工具 
https://www.runoob.com/git
https://zhuanlan.zhihu.com/p/96631135
https://zhuanlan.zhihu.com/p/312875677
---
此文档关于Git使用,以Github作为远程仓库作为示例.

# Git介绍
![[Git流程.png]]

**Workspace**：工作区  
Index / Stage：暂存区  
Repository：仓库区（或本地仓库）  
**Remote**：远程仓库

工作区指处理代码的位置.
暂存区指.git下的index文件
仓库区指本地仓库.


# Git使用

## 准备

首先使用Git生成ssh所需的rsa密钥,并将公钥添加到远程仓库.

## Git提交

1. 使用init对工作区进行初始化
2. 使用add命令,将文件放置到index区
3. 使用commit命令,将工作区同步到本地仓库
4. 使用diff[^diff]指令检查工作区和本地仓库区别(可以放置在前面步骤,看自己习惯)

## Git拉取

1. 使用init对工作区进行初始化
2. 复制远程仓库链接,使用git clone命令,将文件放置到本地仓库
3. 可以先clone再checkout,也可以直接pull到本地





[diff]: https://www.jianshu.com/p/80542dc3164e






