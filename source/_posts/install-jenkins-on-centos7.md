---
title: " install jenkins on centos7\t\t"
url: 330.html
id: 330
comments: false
categories:
  - 未分类
date: 2018-08-17 23:39:06
tags:
---

安装jdk,devel版本的

    yum install java-1.8.0-openjdk-devel
    

添加源

    sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
    sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
    

安装

    yum install jenkins
    

启动

    sudo systemctl start jenkins.service
    

加开机启动

    sudo systemctl enable jenkins.service
    

加防火墙白名单

    sudo firewall-cmd --zone=public --permanent --add-port=8080/tcp
    sudo firewall-cmd --reload