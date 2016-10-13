# git 

### 下载

### 解压

### 安装
1. 更新系统
>yum -y update

2. 安装依赖
>yum -y install curl-devel expat-devel gettext-devel openssl-devel zlib-devel gcc perl-ExtUtils-MakeMaker

3. 编译安装		
将其安装在“/opt/git”目录下
>make prefix=/opt/git all	
make prefix=/opt/git install

4. 设置环境变量
>vi /etc/profile

	在文件的最后一行，添加下面的内容
>export GIT_HOME=/opt/git	
export PATH=${GIT_HOME}/bin:${PATH}

	使用source命令应用修改	
>source /etc/profile

5. 查看版本
>git --version
