---
title: " install docker oracle\t\t"
url: 386.html
id: 386
comments: false
categories:
  - 未分类
date: 2018-10-22 22:07:02
tags:
---

启动方式

    docker run -d -p 49161:1521 wnameless/oracle-xe-11g
    

默认连接方式

    hostname: localhost
    port: 49161
    sid: xe
    username: system
    password: oracle