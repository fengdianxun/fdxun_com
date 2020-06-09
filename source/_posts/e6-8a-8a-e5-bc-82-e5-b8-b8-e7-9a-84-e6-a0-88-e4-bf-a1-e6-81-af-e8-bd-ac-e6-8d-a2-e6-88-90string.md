---
title: " 把异常的栈信息转换成string\t\t"
url: 289.html
id: 289
comments: false
categories:
  - java web
date: 2018-08-09 13:53:49
tags:
---

添加依赖

    compile group: 'commons-lang', name: 'commons-lang', version: '2.6'
    

调用方法

    ExceptionUtils.getFullStackTrace(e)