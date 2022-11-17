# 这是一个用于管理各种云帐户的面板，如az aws do、linode

 安装docker
```
curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh 
```

 如果docker没启动，可以运行这个
```
service docker start
```
 docker创建网络
```
docker network create cdntip_network 
```

 启动mysql容器 (更换mysqlroot密码后，机器内部也需要修改database.conf文件的密码)
```mkdir /data 
docker run -d -it --network cdntip_network -v /data/mysql:/var/lib/mysql --name 数据库名称 -e MYSQL_ROOT_PASSWORD=数据库密码 -e MYSQL_DATABASE=数据库账号 mysql:5.7 --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci
```

 启动 cloudpanel (8111端口可改为任意，此处为实际对外端口)
```
docker run -d -it --network cdntip_network -p 8111:80 --name panel tiktokmjj/openpanel 
```

 进入容器
```
docker exec -it panel /bin/bash
```

 创建管理员
```
python manage.py createsuperuser --username 管理员账户 --email 管理员邮箱
```
示例：python manage.py createsuperuser --username admin --email 123456@qq.com

 添加aws镜像
```
python manage.py aws_update_images
```

# 其他功能
停止当前容器 
```
docker stop panel
```
删除当前容器
```
docker rm panel
```
