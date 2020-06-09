---
title: " hyper-v 网络\t\t"
url: 243.html
id: 243
comments: false
categories:
  - ops
date: 2018-07-20 15:40:20
tags:
---

NAT
---

##### 安装微软提供的驱动插件

[下载地址](https://www.microsoft.com/en-us/download/details.aspx?id=55106 "下载地址")安装方法见pdf

> 如果是winserver 2008 r2下安装centos7，请下载 [LinuxIC-4.2.5-2](https://download.microsoft.com/download/6/8/F/68FE11B8-FAA4-4F8D-8C7D-74DA7F2CFC8C/LinuxIC-4.2.5-2.iso "LinuxIC-4.2.5-2")

##### 在hyper-v管理器里新建虚拟网络交互器,选内部形式

##### 在windows的网络适配器设置里把能上网的网络共享给新建的内部虚拟网卡

##### 进hyper-v的Linux系统里重启network

    systemctl restart network
    

##### 查看有没有生成ip

    ip addr
    

##### ping一下

##### 通过修改网卡文件将dhcp网络改成static，并设置IPADDR,GATEWAY,DNS1

/etc/sysconfig/network-scripts

    BOOTPROTO=static
    ONBOOT=yes
    IPADDR=192.168.137.100
    GATEWAY=192.168.137.1
    DNS1=8.8.8.8
    

##### 重启一下network

    systemctl restart network
    

也可以用dhcp类型,就设置DNS，ip自动获取.

    BOOTPROTO=dhcp
    ONBOOT=yes
    DNS1=8.8.8.8
    

桥接
--

共存
--

nat用dhcp,桥接用静态,不设置gateway