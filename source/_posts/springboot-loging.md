---
title: " springboot loging\t\t"
url: 345.html
id: 345
comments: false
categories:
  - 未分类
date: 2018-08-23 12:35:24
tags:
---

springboot默认使用的log是logback. file指定log文件

    logging.file=/logs/user-logging.log
    

level指定过滤级别，如果写root证明显示所有log，debug代表log的过滤级别。如果不知道自己需要的log在哪个包名下就可以先输出所有的，然后看需要的log在哪个包名下，然后再指定包名。

    logging.level.root=debug
    

也可以level后面跟包名，代表显示这个包名下的log

    logging.level.org.mybatis=debug
    logging.level.org.springframework=info