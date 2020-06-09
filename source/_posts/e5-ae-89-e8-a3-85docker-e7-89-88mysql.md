---
title: " 安装docker版mysql\t\t"
url: 5.html
id: 5
comments: false
categories:
  - docker
date: 2018-05-20 14:48:40
tags:
---

### 通用指令

    docker run -d -p 3306:3306 --restart=always --name mysql -v /home/dockerapp/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=xxx  0d
    

#### 说明:

指令

说明

-d

后台运行

-p 3306:3306

端口映射，冒号前面的是宿主机的端口，后面的是mysql在docker虚拟机的端口，固定的，如果有多个端口那么就写多个-p

--restart=always

自动重启

--name mysql

docker实例的名字

-v /home/dockerapp/mysql:/var/lib/mysql

数据卷映射，冒号前面的是宿主机上的文件位置,后面的是mysql在docker虚拟机里的文件位置，docker虚拟机里的文件位置是固定的 ，如果有多个数据卷就写多个-v

-e MYSQL\_ROOT\_PASSWORD=xxx

环境变量，root账号的密码，是必要的设置，不能少 ，如果有多个环境变量就写多个-e

**指令的结尾是镜像的名字**