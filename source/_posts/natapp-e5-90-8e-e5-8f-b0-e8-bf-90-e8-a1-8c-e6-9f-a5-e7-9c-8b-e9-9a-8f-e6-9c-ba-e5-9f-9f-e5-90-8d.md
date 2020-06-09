---
title: " natapp后台运行查看随机域名\t\t"
url: 46.html
id: 46
comments: false
categories:
  - 内网透传
date: 2018-05-28 21:03:35
tags:
---

1.  注册的service的指令后面是可以加参数的如下 `./natapp -log=-log=stdout`
2.  配置文件config.ini的log参数和logevel参数调整一下 config.ini

    #将本文件放置于natapp同级目录 程序将读取 [default] 段
    #在命令行参数模式如 natapp -authtoken=xxx 等相同参数将会覆盖掉此配置
    #命令行参数 -config= 可以指定任意config.ini文件
    [default]
    authtoken=xxxxxxxx                      #对应一条隧道的authtoken
    clienttoken=                    #对应客户端的clienttoken,将会忽略authtoken,若无请留空,
    log=stdout                        #log 日志文件,可指定本地文件, none=不做记录,stdout=直接屏幕输出 ,默认为none
    loglevel=DEBUG                  #日志等级 DEBUG, INFO, WARNING, ERROR 默认为 DEBUG
    http_proxy=                  #代理设置 如 http://10.123.10.10:3128 非代理上网用户请务必留空
    

3.  systemctl restart后再status就能从log里看到随机域名是什么了