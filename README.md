# 宝塔搭建个人自助云面板，支持Azure Aws Do、Linode等云厂商

安装最新宝塔
```
https://bt.sy/bbs/forum-37-1.html
```

安装Docker

添加镜像
```
xmg66/openpanel3
```
![image](https://user-images.githubusercontent.com/55003092/202558054-8adebdcc-f1b3-4c98-a77b-5e367ed4b380.png)

添加容器

![image](https://user-images.githubusercontent.com/55003092/202558280-837750a2-cdde-4a9f-a602-913efbf2f5bf.png)

安装Mysql5.6 或 Mysql5.7
新建数据库，给数据库设置指定IP访问，填写容器的IP

![image](https://user-images.githubusercontent.com/55003092/202558581-3549f8a6-0ad1-4b38-8570-7e9b4f24ca75.png)

修改cdntip程序中的数据库信息

在Docker的容器列表中，点击目录

![image](https://user-images.githubusercontent.com/55003092/202559414-69fd7979-cdf7-40ac-b628-7797a7b4dff9.png)

访问home/python/panel/config/database.conf文件

[![image]()](https://user-images.githubusercontent.com/55003092/202548258-b8efd278-c3df-484f-b6f9-14985742d139.png)


