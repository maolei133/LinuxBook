# 安装

### 1.1 下载zookeeper
>wget http://www.apache.org/dist/zookeeper/zookeeper-3.4.6/zookeeper-3.4.6.tar.gz

### 1.2 解压文件
>tar zxvf zookeeper-3.4.6.tar.gz

### 1.3 把zookeeper-3.4.6/conf下的zoo_sample.cfg复制一个zoo.cfg的文件
>cd zookeeper-3.4.6/conf/    
cp zoo_sample.cfg zoo.cfg

### 1.4 启动Zookeeper 的服务
>cd ../bin/    
./zkServer.sh start