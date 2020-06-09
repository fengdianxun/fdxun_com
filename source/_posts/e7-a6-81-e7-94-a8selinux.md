---
title: " 禁用selinux\t\t"
url: 161.html
id: 161
comments: false
categories:
  - centos
date: 2018-06-19 12:52:50
tags:
---

定位文件

    vi /etc/sysconfig/selinux
    

编辑文件

    SELINUX=disabled
    

重启系统

    reboot