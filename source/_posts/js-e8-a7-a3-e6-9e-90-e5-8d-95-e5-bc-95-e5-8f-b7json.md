---
title: " js解析单引号json\t\t"
url: 250.html
id: 250
comments: false
categories:
  - react-native
date: 2018-07-21 12:39:20
tags:
---

    "﻿{'tag':null,'user':'137239','code':'0','message':'登陆成功','token':'69af86a661e76448b177767db58c4bcc'}"
    

JSON.parse可以解析普通的双引号json,像这种单引号的json需要采用另一种解析方式。

    eval("("+text+")")
    

如果用react-native的fetch框架获取数据时不能用response.json()直接取json对象,因为解析不出来，需要用response.text()先取出string来然后发现是单引号的json字符串然后选择eval函数解析成json对象。