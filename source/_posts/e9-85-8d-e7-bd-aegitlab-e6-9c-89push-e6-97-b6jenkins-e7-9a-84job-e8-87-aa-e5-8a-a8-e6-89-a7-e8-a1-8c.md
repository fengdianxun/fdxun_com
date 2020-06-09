---
title: " 配置gitlab有push时Jenkins的job自动执行\t\t"
url: 322.html
id: 322
comments: false
categories:
  - 未分类
date: 2018-08-17 08:59:20
tags:
---

### jenkins

Build Triggers用remotely模式，然后按格式填写url，此处的url是被调用的，意思是通过这个url就能通知jenkins执行job。 格式如下,JENKINS_URL填可以被调用的，token自己定义

    JENKINS_URL/job/user/build?token=TOKEN_NAME
    

示例

    http://192.168.1.211:8080/job/user/build?token=xxxx
    

### gitlab

settings->intergrations添加一个webhook， url格式如下,USERNAME就是用户名，USER\_API\_KEY是用对应可以操作接口的key，在jenkins管理页面的用户页面的Configure的API Token。

    http://USERNAME:USER_API_TOKEN@SERVER_URL/job/user/build