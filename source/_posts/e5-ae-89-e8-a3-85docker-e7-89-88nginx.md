---
title: " 安装docker版nginx\t\t"
url: 14.html
id: 14
comments: false
categories:
  - docker
  - nginx
date: 2018-06-19 10:56:35
tags:
---

1.  下载镜像 `docker pull nginx`
    
2.  运行镜像 `docker run -d -P --name nginx cd52`
    
3.  新建目录，并进入目录 `mkdir nginx` `cd nginx`
    
4.  拷贝配置到当前目录,.代表当前目录
    

`docker cp nginx:/etc/nginx .`

5.  停止并删除nginx容器 `docker rm -f nginx`
    
6.  目录改名conf `mv nginx conf`
    
7.  新建容器，把当前目录加卷 `docker run --name nginx -d -p 9012:80 -v /root/nginx/html:/usr/share/nginx/html -v /root/nginx/conf:/etc/nginx cd52`

如果遇到/etc/nginx/nginx.conf权限问题打不开需要禁用selinux。