# mysql-docker

* mysql8 的docker  镜像文件

* 密码加密规则：mysql_native_password
* 去除sql_mode ： ONLY_FULL_GROUP_BY 分组限制


# 镜像启动 
> docker pull nuiiqk/mysql

[自动重启启动]
> docker run --restart=always --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=数据库密码 -d nuiiqk/mysql:latest

# 进入docker镜像
> docker exec -it [镜像ID] bash
