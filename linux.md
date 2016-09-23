# linux 安装与配置

输入命令
#vi /etc/sysconfig/network-scripts/ifcfg-eth0 [编辑网卡的配置文件]
输入上述命令后回车，打开配置文件，使用方向键移动光标到最后一行，按字母键“O”，进入编辑模式，输入以下内容：
IPADDR=192.168.4.10
NETMASK=255.255.255.0
GATEWAY=192.168.4.1
另外光标移动到”ONBOOT=no”这一行，更改为ONBOOT=yes
“BOOTPROTO=dhcp”，更改为BOOTPROTO=none
完成后，按一下键盘左上角ESC键，输入:wq 在屏幕的左下方可以看到，输入回车保存配置文件。

之后需要重启一下网络服务，命令为
#service network restart

