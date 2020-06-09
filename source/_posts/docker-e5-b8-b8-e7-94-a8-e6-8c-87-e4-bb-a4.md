---
title: " docker常用指令\t\t"
url: 205.html
id: 205
comments: false
categories:
  - docker
date: 2018-07-13 21:20:21
tags:
---

复制docker内的文件夹到宿主机，不要漏掉点，点代表当前目录

    docker cp 实例名:/var/nginx .
    

进入docker实例内部

    docker exec -it 实例名 bash
    

删除私有仓库里的镜像

    docker exec -it 私有仓库容器名 rm -rf /var/lib/registry/docker/registry/v2/repositories/镜像名
    

#### docker run

host网络模式

    --net host
    

自启动

    --restart=always