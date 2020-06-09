---
title: " docker的网络设置\t\t"
url: 211.html
id: 211
comments: false
categories:
  - docker
date: 2018-07-13 11:23:41
tags:
---

常用网络有none、host、bridge、container

    --net host
    特殊指定host网络
    

模式

含义

none

不需要对外

host

仅主机网路，不需要做端口映射，直接用宿主机的端口，需要主动设置防火墙白名单

bridge

用的是nat网络，-p指定，不需要配置防火墙，自动就可以访问

    #直接设置dns
    --dns 8.8.8.8