# Docker基本操作



##### 入门手册：

http://docker.easydoc.net

##### 配置镜像加速源：

在设置 - Docker Engine 中添加 ```"registry-mirrors":["https://registry.docker-cn.com","https://docker.mirrors.ustc.edu.cn"],```

##### Docker 镜像仓库

https://hub.docker.com/

##### Docker 官方镜像仓库查找 Redis 

docker run -d -p 6379:6379 --name redis redis:latest

其中 latest 代表版本号替换

##### WordPress 安装

在docker 目录下  ````docker-compose up -d```

