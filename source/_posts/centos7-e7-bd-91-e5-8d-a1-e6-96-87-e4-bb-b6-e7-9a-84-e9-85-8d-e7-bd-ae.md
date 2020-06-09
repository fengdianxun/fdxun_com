---
title: " centos7网卡文件的配置\t\t"
url: 269.html
id: 269
comments: false
categories:
  - centos
date: 2018-08-01 16:55:35
tags:
---

文件位置

    /etc/sysconfig/network-scripts
    

静态ip

    DEVICE=eno16777736
    BOOTPROTO=static
    ONBOOT=yes
    TYPE=Ethernet
    IPADDR=192.168.76.8
    NETMASK=255.255.255.0
    GATEWAY=192.168.76.2
    DNS1 =8.8.8.8