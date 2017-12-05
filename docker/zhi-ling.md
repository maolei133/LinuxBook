查看版本

docker -v

启动docker

service docker status

查询镜像

docker search 名称

拉取镜像

docker pull 镜像名称

查看已有镜像

docker images

查看所有进程

docker ps -a

停止所有容器

docker stop $\(docker ps -a -q\)

删除所有容器

docker rm $\(docker ps -a -q\)

