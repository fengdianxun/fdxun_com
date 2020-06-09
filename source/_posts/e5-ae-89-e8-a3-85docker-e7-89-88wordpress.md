---
title: " 安装docker版wordpress\t\t"
url: 12.html
id: 12
comments: false
categories:
  - docker
date: 2018-05-20 15:07:04
tags:
---

### 指令

    docker run --name wordpress --restart=always -d -p 81:80 -e WORDPRESS_DB_NAME=wordpress -e WORDPRESS_DB_HOST=172.21.0.1 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD='xxxxxxx' -v /home/dockerapp/wordpress:/var/www/html 61
    

指令

含义

--name wordpress

实例名字

--restart=always

自动重启

-p 81:80

端口映射，虚拟机内的80对应宿主机的81，wordpress默认占用80端口

-e WORDPRESS\_DB\_NAME=wordpress

需要先建一个mysql数据库，名字在这里指定

-e WORDPRESS\_DB\_USER=root

数据库的用户名

-e WORDPRESS\_DB\_PASSWORD='xxxxxxx'

数据库的密码

-v

代码文件映射到宿主机

指令末端是镜像的名字