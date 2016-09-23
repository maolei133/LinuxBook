# 配置 maven

## 1.打开配置文件
> vi /etc/profile

## 2.配置
>export MAVEN_HOME=/opt/apache-maven-3.3.9	
export PATH=${MAVEN_HOME}/bin:${PATH}

## 3.生效		
>source /etc/profile

## 4.验证		
>mvn -v
