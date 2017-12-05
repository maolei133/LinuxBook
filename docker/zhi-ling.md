| 简介 | 指令 |
| :--- | :--- |
| 查看版本 | docker -v |
| 查看状态 | service docker status |
| 查询镜像 | docker search 镜像名称 |
| 拉取镜像 | docker pull 镜像名称 |
| 查看已有镜像 | docker images |
| 查看所有容器 | docker ps -a |
| 查看启动容器 | docker ps |
| 停止启动容器 | docker stop $\(docker ps -q\) |
| 停止所有容器 | docker stop $\(docker ps -a -q\) |
| 删除所有容器 | docker rm $\(docker ps -a -q\) |
| 停用并删除容器 | docker stop $\(docker ps -q\) & docker rm $\(docker ps -aq\) |
| 构建镜像命令 | docker build -t 镜像名称 -f dockerfile文件名称 . |



