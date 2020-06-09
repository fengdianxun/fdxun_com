---
title: " centos7安装gradle\t\t"
url: 305.html
id: 305
comments: false
categories:
  - 未分类
date: 2018-08-14 11:19:16
tags:
---

下载安装包到本地

    wget https://downloads.gradle.org/distributions/gradle-4.9-bin.zip
    

创建gradle目录

    sudo mkdir /opt/gradle
    

解压

    sudo unzip -d /opt/gradle gradle-4.9-bin.zip
    

添加环境变量

    export PATH=$PATH:/opt/gradle/gradle-4.9/bin
    

运行指令看版本号

    gradle -v