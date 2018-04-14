* ##### Vi方向键变乱码、删除键不能使用的解决方法

> 修改\# vi /etc/vim/vimrc.tiny  
> set compatible 改为 set nocompatible  
> 添加 set backspace=2

* ##### 配置网络

> 修改 /etc/network/interfaces，增加以下内容：
>
> auto eth0
>
> iface eth0 inet dhcp
>
> 然后，启动网络接口：
>
> ifup eth0
>
> 查询ip地址：
>
> ip addr

* ##### 更改debian的软件源sources.list

> http://mirrors.163.com/.help/debian.html
>
> /etc/apt/sources.list

* ##### 1



