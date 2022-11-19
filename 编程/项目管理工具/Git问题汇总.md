#Git 

---
# Failed to connect to github.com port 443:connection timed out
2022年09月29日23:09
出现此问题大概率是网络代理问题,解决途径如下:

```shell
git config --global --unset http.proxy
git config --global --unset https.proxy
```

取消网络代理即可.

# OpenSSL SSL_read: Connection was reset, errno 10054
2022年10月01日20:10
出现此问题大概率是网络代理问题,解决途径如下:

git config --list 查看 http.sslVerify 的值是否为false，如果为true或者是flase之类的拼写错误，打开git使用`git config --global http.sslVerify “false” `命令修改设置，解除ssl验证。

```shell
git config --global --unset
```