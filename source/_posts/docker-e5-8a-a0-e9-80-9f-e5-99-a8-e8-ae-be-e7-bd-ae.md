---
title: " docker加速器设置\t\t"
url: 25.html
id: 25
comments: false
categories:
  - docker
date: 2018-07-13 21:18:59
tags:
---

    vi /etc/docker/daemon.json
    

内容如下，json格式

    {
        "registry-mirrors": ["https://registry.docker-cn.com"]
    }
    

registry-mirrors对应的值是加速器的数组，json结构. 添加不检查安全性的源(私有仓库)

    {
    
      "insecure-registries": [
        "192.168.1.67:5000"
      ]
    
    }