# 配置

## 2.1 单机配置

### 2.1.1 安装
按照第一点安装好zookeeper

### 2.1.2 

## 2.2 集群配置

这里以三台CentOS机器为例搭建一个最小的集群环境，三台服务器或者三台虚拟机均可。	
假设它们的IP地址分别为	
192.168.1.133	
192.168.1.134	
192.168.1.135	

### 2.2.1 安装
在三台机器上按照第一点安装好zookeeper

### 2.2.2 修改配置文件
修改zoo.cfg文件
>
dataDir=/usr/local/zookeeper/zookeeper-3.4.6/data	
clientPort=2181		
server.1=192.168.1.133:2888:2999	
server.2=192.168.1.134:2888:2999	
server.3=192.168.1.135:2888:2999	

133修改clientPort为3001
> clientPort=3001

134修改clientPort为3002
> clientPort=3002

135修改clientPort为3003
> clientPort=3002

因为是在三台虚拟机所以clientPort可以都使用默认的2181端口，如果是一台机器跑三个zookeeper就需要修改成三个不同的端口

### 2.2.3 创建myid文件
用“touch”命令在三台机器上dataDir目录下创建myid文件

### 2.2.4 启动Zookeeper
执行命令“./zkServer.sh start”将会启动Zookeeper

执行命令“./zkServer.sh status”查看Zookeeper集群状态，如下所示：
>192.168.1.133	
JMX enabled by default	
Using config: /usr/local/zookeeper/zookeeper-3.4.6/bin/../conf/zoo.cfg	
Mode: follower

>192.168.1.134	
JMX enabled by default	
Using config: /usr/local/zookeeper/zookeeper-3.4.6/bin/../conf/zoo.cfg	
Mode: follower

>192.168.1.135	
JMX enabled by default	
Using config: /usr/local/zookeeper/zookeeper-3.4.6/bin/../conf/zoo.cfg	
Mode: leader


## 3 注意事项
zookeeper不管单节点还是多节点机器配置起来就是很简单的，因为是linux系统在配置完成之后不要忘记打开端口

vi /etc/sysconfig/iptables

>192.168.1.133	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 2888 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 2999 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 3001 -j ACCEPT		
-A INPUT -m state --state NEW -m tcp -p tcp --dport 8080 -j ACCEPT		
-A INPUT -m state --state NEW -m tcp -p tcp --dport 20880 -j ACCEPT

>192.168.1.134	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 2888 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 2999 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 3002 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 8080 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 20880 -j ACCEPT

>192.168.1.135	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 2888 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 2999 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 3003 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 8080 -j ACCEPT	
-A INPUT -m state --state NEW -m tcp -p tcp --dport 20880 -j ACCEPT

service iptables restart	最后重启防火墙

