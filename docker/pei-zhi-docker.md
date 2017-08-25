# 配置docker

### 1.创建docker账户

> useradd docker -d /home/docker -s /bin/bash

### 2.设置docker账户密码

> echo "docker:docker" \| chpasswd

### 3.配置mysql

###### 3.1 查询mysql的镜像

> docker search mysql

###### 3.2 获取mysql镜像

> docker pull mysql

###### 3.3 指定配置启动

> docker run --name mysql -p 3306:3306 -e MYSQL\_ROOT\_PASSWORD=123456 -d mysql:latest
>
> 命令说明：
>
> * **-p 3306:3306：**将容器的3306端口映射到主机的3306端口
>
> * **-e MYSQL\_ROOT\_PASSWORD=123456：**初始化root用户的密码

### 4.配置ActiveMQ

###### 4.1 查询ActiveMQ的镜像

> docker search activemq

###### 4.2 获取ActiveMQ镜像

> docker pull webcenter/activemq

###### 4.3 指定配置启动

> docker run --name activemq -p 8161:8161 -p 61616:61616 -e ACTIVEMQ\_ADMIN\_LOGIN=admin -e ACTIVEMQ\_ADMIN\_PASSWORD=123456 --restart=always -d webcenter/activemq:latest
>
> 命令说明：
>
> * **-p **8161**:**8161**：**将容器的3306端口映射到主机的8161端口
>
> * **-p** 61613:61613**：**将容器的3306端口映射到主机的61613端口
>
> * **-e ACTIVEMQ\_ADMIN\_LOGIN=admin：**初始化用户的名称
>
> * **-e ACTIVEMQ\_ADMIN\_PASSWORD=123456：**初始化用户的密码
>
> * **--restart=always：**开机自动启动



