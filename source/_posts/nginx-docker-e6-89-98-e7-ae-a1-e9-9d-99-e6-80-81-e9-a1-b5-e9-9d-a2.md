---
title: " nginx docker 托管静态页面\t\t"
url: 273.html
id: 273
comments: false
categories:
  - 未分类
date: 2018-08-02 17:19:00
tags:
---

### Dockerfile

COPY的意思是把docker上下文里的文件或者文件夹复制到镜像对应的地方。此处后面的路径都是nginx默认的文件夹结构。

    FROM nginx:alpine
    EXPOSE 80
    COPY default.conf /etc/nginx/conf.d/default.conf
    COPY /src/main/webapp /usr/share/nginx/html
    

### default.conf

首页改成第一个要打开的页面，比如index.html

    location / {
            root   /usr/share/nginx/html;
            index  /pages/buy.html;
        }
    

### 打镜像

不要漏掉点儿，点代表上下文为当前目录.

    docker build -t 镜像名:版本号 .