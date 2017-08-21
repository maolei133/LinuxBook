# 安装mysql

### 1.下载仓库

[下载地址](http://dev.mysql.com/downloads/repo/yum/)

### 2.安装仓库

> yum localinstall mysql57-community-release-el6-8.noarch.rpm

### 3.查看可安装的mysql

> yum repolist enabled \| grep "mysql._-community._"

### 4.安装

> 安装最新的版本，那么可以直接执行  
> yum install mysql-community-server
>
> 如果我们要选择版本，可以先执行下面这个命令查看一下有哪些版本  
> yum repolist all \| grep mysql
>
> 信息如下，默认启用5.7版本的mysql  
> mysql55-community    MySQL 5.5 Community Server    disabled  
> mysql56-community    MySQL 5.6 Community Server    disabled  
> mysql57-community    MySQL 5.7 Community Server    enabled:    282
>
> 如果要安装5.6版本的mysql，用命令启用5.6版本，禁用5.7版本  
> yum-config-manager --enable mysql56-community  
> yum-config-manager --disable mysql57-community
>
> 系统默认没有这个命令，这个命令在yum-utils 包里  
> 用命令时报错  
> -bash: yum-config-manager: command not found
>
> 通过命令安装yum-utils  
> yum -y install yum-utils
>
> 配置完成后执行命令安装mysql  
> yum install mysql-community-server
>
> 启动mysql  
> service mysqld start
>
> 查看mysql状态  
> service mysqld status
>
> 重启mysql  
> service mysqld restart

### 5.安装错误

```
1. 提示 Requires: libstdc++.so.6(GLIBCXX_3.4.15)(64bit)
   升级gcc：http://blog.liudongkai.com/2014/05/12/GLIBCXX-not-found/
   或升级libstdc：http://blog.liudongkai.com/2014/05/12/GLIBCXX-not-found/
   下载 wget http://ftp.de.debian.org/debian/pool/main/g/gcc-4.7/libstdc++6_4.7.2-5_amd64.deb
   假设下载的文件放在/data0/software/
   解压：ar -x libstdc++6_4.7.2-5_amd64.deb && tar xvf data.tar.gz
   cd  /data0/software/usr/lib/x86_64-linux-gnu
   cp libstdc++.so.6.0.17 /usr/lib64
   cd /usr/lib64/
   rm -f libstdc++.so.6
   ln -s libstdc++.so.6.0.17 libstdc++.so.6
   ll libstdc*
```



