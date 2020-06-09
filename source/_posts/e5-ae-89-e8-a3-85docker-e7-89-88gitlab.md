---
title: " 安装docker版gitlab\t\t"
url: 315.html
id: 315
comments: false
categories:
  - 未分类
date: 2018-08-16 13:09:45
tags:
---

先用docker pull拉取镜像

    docker pull gitlab/gitlab-ce
    

运行镜像镜像,映射端口和目录,默认配置的gitlab会起80端口，先映射出来后期可以修改。-v不用提前创建目录，docker会自动绑创建。

    docker run -d -p 180:80 -v /root/gitlab/config:/etc/gitlab -v /root/gitlab/data:/var/opt/gitlab -v /root/gitlab/log:/var/log/gitlab --privileged=true --restart always --name gitlab 966f4a515457
    

如果说想改docker内部的gitlab的端口号或者.git源的路径就需要改配置文件。直接改映射出来的/root/gitlab/config/gitlab.rb文件的

     external_url 'http://fdxun.com:180'
    

然后进入容器重启配置，会自动解析配置的url的端口号，然后按照这个端口号起服务

    docker exec -it gitlab bash
    gitlab-ctl reconfigure