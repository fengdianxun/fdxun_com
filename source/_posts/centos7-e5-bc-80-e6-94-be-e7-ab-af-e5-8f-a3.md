---
title: " centos7开放端口\t\t"
url: 207.html
id: 207
comments: false
categories:
  - centos
date: 2018-07-13 11:12:44
tags:
---

查看已经开放的端口

    firewall-cmd --list-ports
    

开启端口

    firewall-cmd --zone=public --add-port=80/tcp --permanent
    

移除端口

    firewall-cmd --zone=public --remove-port=80/tcp --permanent
    

重启防火墙

    firewall-cmd --reload