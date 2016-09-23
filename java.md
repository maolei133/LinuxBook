# java 安装与配置


1.yum安装jdk，默认安装在/usr/lib/jvm/
yum install java-1.7.0-openjdk

2.设置环境变量
vi /etc/profile

JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk-1.7.0.75.x86_64
JRE_HOME=$JAVA_HOME/jre
CLASS_PATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib
PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
export JAVA_HOME JRE_HOME CLASS_PATH PATH

配置生效
source /etc/profile
