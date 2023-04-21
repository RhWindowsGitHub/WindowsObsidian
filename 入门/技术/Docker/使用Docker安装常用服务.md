

```ad-summary
title:概述
使用 Docker 安装常用服务
```

# 一、使用Docker安装常用服务

```ad-tip
title:INFO
作者：Cola

时间：2023-04-16 10:37 
```

```ad-todo
title:Features： 🐔
 - [x] Mysql
 - [x] Redis
 - [x] Nginx
```

##  1.1 Mysql 的安装与配置

1. 拉取 Mysql 镜像 `docker pull mysql`
2. 创建容器卷 `docker volume create mysql8_3306`
3. 创建 Docker 网络 `docker network create mysql8-net`
4. 运行 Docker 容器 

```shell
docker run -d --name mysql8_3306 -e MYSQL_ROOT_PASSWORD=root -v mysql8_3306:/var/lib/mysql -p 3306:3306 --network=mysql8-net <镜像 id>
```


## 1.2 redis 的安装与配置

1. 拉取 Redis 镜像 `docker pull redis:6.0.8`
2. 创建容器卷 `docker volume create redis6_6379`
3. 创建 Docker 网络 `docker network create redis6-net`

4. 自定义配置

> 1. 使用 `docker volume inspect redis6_6379` 查看容器卷的详细信息
> 2. 进入相关目录 `cd /var/lib/docker/volumes/redis6_6379/_data`
> 3. 创建 redis.conf 文件 `vim redis.conf` 输入 [[Redis 配置文件]] 文件中的内容

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416110553.png)

5. 运行 Docker 容器

```shell
docker run -d --name redis6_6379 -v redis6_6379:/usr/local/redis -p 6379:6379 --network=redis6-net <镜像 id> redis-server /usr/local/redis/redis.conf
```

## 1.3 Nginx 的安装与配置

1. 拉取 Nginx 镜像 `docker pull nginx`
2. 创建容器卷 `docker volume create nginx_80`
3. 创建 Docker 网络 `docker network create nginx-net`

4. 自定义配置

> 1. 使用 `docker volume inspect nginx_80` 查看容器卷的详细信息
> 2. 进入相关目录 `cd /var/lib/docker/volumes/nginx_80`
> 3. 创建 nginx.conf 文件 `vim nginx.conf` 输入 [[Nginx 配置文件]] 文件中的内容
> 4. 使用 `mkdir conf.d` 创建 conf.d 文件夹 `vim default.conf` 输入 [[default.conf]] 文件中的内容

5. 运行 Docker 容器

```ad-danger
title: 注意：
因为 Docker -v 命令不支持使用容器卷名称直接映射文件所以此处使用容器卷的绝对位置进行映射，容器卷的绝对路径的查看可以参考 [[使用Docker安装常用服务#1.2 redis 的安装与配置]] 中的第四步
```

```shell
docker run -d --name nginx_80 -v <容器卷绝对位置>/html:/usr/share/nginx/html -v <容器卷绝对位置>/nginx.conf:/etc/nginx/conf.conf -v <容器卷绝对位置>/conf.d:/etc/nginx/conf.d -p 80:80 --network=nginx-net <镜像 id>
```

