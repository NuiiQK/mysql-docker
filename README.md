# mysql-docker

* mysql8 的docker  镜像文件

* 密码加密规则：mysql_native_password
* 去除sql_mode ： ONLY_FULL_GROUP_BY 分组限制


# 镜像启动 
> docker pull nuiiqk/mysql

# 创建文件夹
mkdir -p {/app/docker/data/mysql/data,/app/docker/data/mysql/files,/app/docker/data/mysql/logs}

[自动重启启动]
> docker run --restart=always --privileged --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=密码 -e TZ=Asia/Shanghai -v /app/docker/data/mysql/data:/var/lib/mysql:rw -v /app/docker/data/mysql/files:/var/lib/mysql-files:rw -v /app/docker/data/mysql/logs:/var/log/mysql:rw -v /etc/localtime:/etc/localtime:ro -d nuiiqk/mysql:latest

# 进入docker镜像
> docker exec -it [镜像ID] bash

