# 配置mysql

### 1. 修改root密码为123456

&gt;  
update mysql.user set password=PASSWORD\('123456'\) where User='root';  
flush privileges;

### 2. 创建用户

> insert into mysql.user\(Host,User,Password\) values\("localhost","test",password\("123456"\)\);
>
> 如果报错：ERROR 1364 \(HY000\): Field 'ssl\_cipher' doesn't have a default value  
> 原因：在配置文件my.cnf中有这样一条语句sql\_mode=NO\_ENGINE\_SUBSTITUTION,STRICT\_TRANS\_TABLES  
> 指定了严格模式，为了安全，严格模式禁止通过insert 这种形式直接修改mysql库中的user表进行添加新用户

&gt;  
解决办法：将配置文件中的STRICT\_TRANS\_TABLES删掉  
sql\_mode=NO\_ENGINE\_SUBSTITUTION  
然后重启mysql即可

### 3. 用户授权：grant 权限 on 数据库.\* to 用户名@登录主机 identified by "密码"

&gt;  
grant all privileges on \*.\* to 'test'@'%' identified by '123456';  
flush privileges;

### 4. 修改防火墙，开启3306端口

&gt;  
vi /etc/sysconfig/iptables

> 添加端口至倒数第三行之上  
> -A INPUT -m state --state NEW -m tcp -p tcp --dport 3306 -j ACCEPT
>
> 重启服务  
> service iptables restart

### 5.查询初始化密码

> grep 'temporary password' /var/log/mysqld.log



