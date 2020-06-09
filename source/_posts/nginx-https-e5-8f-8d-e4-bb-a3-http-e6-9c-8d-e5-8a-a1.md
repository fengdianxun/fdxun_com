---
title: " nginx https 反代 http服务\t\t"
url: 377.html
id: 377
comments: false
categories:
  - 未分类
date: 2018-09-12 16:38:35
tags:
---

主要是**proxy_redirect off**起作用

    location / {
            proxy_pass http://127.0.0.1:8080;
            proxy_redirect off；
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto https;
        }