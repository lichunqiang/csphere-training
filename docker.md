```
//首先将项目clone到本地

cd docker-training

cd centos7/
```
### FROM 指令

父镜像

### MAINTAINER 

维护者

### ENV

TZ "Asia/Shanghai"

ENV TEAM xterm

ADD 比copy多两个功能：



生成一个镜像:版本号「默认为lastest」

docker build -t registry_url/csphere/centos:7.1

eg: docker build -t csphere/centos:7.1 [./Dockerfile]

docker images # 查看当前构建好的镜像


### 生成镜像容器

docker run -it 

[-d 在后端启动，返回container ID号]

-p 2222:22 

--name base csphere/centos:7.1

查看容器信息

docker ps -a

### php-fpm

docker build -t csphere/php-fpm:5.4

docker run -d -p 8080:80 --name webserver csphere/php-fpm:5.4

### mysql
docker build -t csphere/mysql:5.5

> docker run -d -p 3306:3306 -v host_dir:container_dir

docker run -d -p 3306:3306 -v /var/lib/docker/vfs/dir/mydata:/var/lib/mysql csphere/mysql:5.5

### 进入交互式模式

docker exec -it website[container] /bin/bash

docker exec -it dbserver /bin/bash

### 删除container

docker rm -f dbserver

### wordpress

docker build -t csphere/wordpress:4.2 .

docker run -d -p 80:80 --name wordpress -e WORDPRESS_DB_HOST=10.12.233.32 -e WORDPRESS_DB_USER=admin -e WORDPRESS_DB_PASSWORD=csphere2015 csphere/wordpress:4.2

### 删除镜像

docker images

docker rmi container-name

[其他笔记](20150604_other.md)
