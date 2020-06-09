---
title: " nginx和frp共享80端口\t\t"
url: 153.html
id: 153
comments: false
categories:
  - nginx
date: 2018-06-19 12:52:30
tags:
---

一台主机的情况下共用80端口，这里要借助域名。 把80端口交给nginx,然后frp的http服务起其他端口比如8888。 nginx通过反代映射给frp。

    server {
        listen       80;
        server_name  *.oxoxo.xyz;
    
        location / {
            proxy_pass      http://127.0.0.1:8888;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        }
    }
    

这里需要注意的是frp只能用二级域名做透传，不支持一级域名。 而且一般一级域名也都是要留给自己对一些服务做介绍用，比如我可以在主页里介绍这个透传服务。 为了使自起服务和透传的服务共用80端口就需要再建一个nginx的配置文件，也监听80端口但是域名不一样，我们这里可以用主域名。

    server {
        listen       80;
        server_name  www.oxoxo.xyz oxoxo.xyz;
    
        location / {
            proxy_pass      http://127.0.0.1:8000;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        }
    }
    

8000就是我起的frps的http服务，用来描述内网透传服务用的。 这个2段代码可以分别建.conf文件，放在/nginx/conf/conf.d目录下，比如default.conf、default1.conf，然后运行nginx就会自动加载这2个配置文件，根据不同的域名走不同的代理配置。