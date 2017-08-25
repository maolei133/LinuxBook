# 配置docker 

### 1.创建docker账户

> useradd docker -d /home/docker -s /bin/bash

### 2.设置docker账户密码

> echo "docker:docker" \| chpasswd

### 3.配置mysql

> \#查询mysql的镜像
>
> docker search mysql
>
> \#拉取mysql镜像
>
> docker pull mysql
>
> \#指定配置启动
>
> docker run -p 3306:3306 --name mymysql -e MYSQL\_ROOT\_PASSWORD=123456 -d mysql:latest
>
> 命令说明：
>
> * **-p 3306:3306：**将容器的3306端口映射到主机的3306端口
>
> * **-e MYSQL\_ROOT\_PASSWORD=123456：**初始化root用户的密码

### 4.配置ActiveMQ

> \#查询ActiveMQ的镜像
>
> docker search activemq
>
> \#拉取ActiveMQ镜像
>
> docker pull webcenter/activemq
>
> \#指定配置启动
>
> docker run -p 8161:8161 -p 61613:61613 --name mymysql -e MYSQL\_ROOT\_PASSWORD=123456 -d mysql:latest
>
> 命令说明：
>
> * **-p **8161**:**8161**：**将容器的3306端口映射到主机的8161端口
>
> * **-p** 61613:61613**：**将容器的3306端口映射到主机的61613端口
>
> * **-e MYSQL\_ROOT\_PASSWORD=123456：**初始化root用户的密码



