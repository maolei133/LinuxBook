# docker指令

| 简介 | 指令 |
| :--- | :--- |
| 查看版本 | docker -v |
| 启动docker | systemctl start docker |
| 查看状态 | systemctl status docker |

# 镜像指令

| 简介 | 指令 |
| :--- | :--- |
| 查询服务器镜像 | docker search 镜像名称 |
| 拉取服务器镜像 | docker pull 镜像名称 |
| 查看本地镜像 | docker images |
| 构建镜像命令 | docker build -t &lt;REPOSITORY:tag&gt; -f dockerfile文件名称 .     docker build -t &lt;REPOSITORY:tag&gt; . |
| 删除所有镜像 | docker rmi $\(docker images -q\) |

# 容器指令

| 简介 | 指令 |
| :--- | :--- |
| 启动容器 | docker run &lt;REPOSITORY&gt; |
| 进入容器 | docker exec -it &lt;CONTAINER ID&gt; /bin/bash |
| 启动并进入容器 | docker run -it --rm=true &lt;REPOSITORY&gt; /bin/bash |
| 停止容器 | docker stop $\(docker ps -q\) |
| 删除容器 | docker rm $\(docker ps -aq\) |
| 停用并删除容器 | docker stop $\(docker ps -q\) && docker rm $\(docker ps -aq\) |
| 查看所有容器 | docker ps -a |
|  |  |



