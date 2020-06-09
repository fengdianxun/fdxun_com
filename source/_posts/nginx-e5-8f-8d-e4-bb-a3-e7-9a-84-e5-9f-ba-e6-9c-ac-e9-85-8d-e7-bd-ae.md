---
title: " nginx反代的基本配置\t\t"
url: 147.html
id: 147
comments: false
categories:
  - nginx
date: 2018-06-19 12:54:32
tags:
---

    server {
      listen 80;
      server_name www.fdxun.com;
    
      location / {
        proxy_pass http://localhost:8081;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
      }
    }