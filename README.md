# mysql-docker

* mysql8 的docker  镜像文件

* 密码加密规则：mysql_native_password
* 去除sql_mode ： ONLY_FULL_GROUP_BY 分组限制


# 镜像启动 
> docker pull nuiiqk/mysql

[自动重启启动]
> docker run --restart=always --privileged --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=数据库密码 -e TZ=Asia/Shanghai -v [/app/docker/data/mysql/data本地磁盘]:/var/lib/mysql:rw -v /app/docker/data/mysql/fiels:/var/lib/mysql-files:rw -v /app/docker/data/mysql/logs:/var/log/mysql:rw -v /etc/localtime:/etc/localtime:ro -d nuiiqk/mysql:latest

# 进入docker镜像
> docker exec -it [镜像ID] bash

# 防止容器崩溃-可以进行以下操作：
## 查询数据库存放目录
> mysql -uroot -p
> # Enter password:

> show variables like '%datadir%';


## 拷贝容器配置文件
> docker cp mysql:/etc/mysql /usr/local/mysql/conf

## 数据映射到指定目录
> docker stop mysql   
> docker rm mysql   
> docker run --restart=always --name mysql -p 3306:3306 -v 本地配置路径:/etc/mysql -v 本地存放数据路径:/var/lib/mysql/ -e MYSQL_ROOT_PASSWORD=数据库密码 -d nuiiqk/mysql:latest

