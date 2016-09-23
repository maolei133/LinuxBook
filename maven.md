# maven 安装与配置



### 安装

1. 安装
>vi /etc/profile

2. 配置
>export MAVEN_HOME=/opt/apache-maven-3.3.9	
export PATH=${MAVEN_HOME}/bin:${PATH}

3. 生效		
>source /etc/profile

4. 验证		
>mvn -v