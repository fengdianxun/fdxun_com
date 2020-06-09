---
title: " 查端口占用\t\t"
url: 126.html
id: 126
comments: false
categories:
  - ops
date: 2018-06-19 12:57:41
tags:
---

### centos7

#### 端口

    ss -lnp|grep 4567
    

#### 查进程

     ps -ef|grep 4766
    

### windows

#### 端口

    netstat -aon|findstr "9050"
    

#### 查进程

    tasklist|findstr "2016"