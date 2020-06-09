---
title: " nginx配置文件配置共用80端口\t\t"
url: 17.html
id: 17
comments: false
categories:
  - nginx
date: 2018-05-28 21:14:12
tags:
---

1.  先修改监听的端口号，即共用的端口号，http.server.listen的值改成80
2.  添加子服务器,新建location，每一个location代表一种匹配方式，如果访问能够匹配上则会跳转到proxy_pass定义的其他端口号提供的服务上去，location可以写多个

    #user       www www;  ## Default: nobody
        worker_processes  5;  ## Default: 1
        error_log  logs/error.log;
        pid        logs/nginx.pid;
        worker_rlimit_nofile 8192;
    
        events {
          worker_connections  4096;  ## Default: 1024
        }
    
        http {
    
          default_type application/octet-stream;
          log_format   main '$remote_addr - $remote_user [$time_local]  $status '
            '"$request" $body_bytes_sent "$http_referer" '
            '"$http_user_agent" "$http_x_forwarded_for"';
          access_log   logs/access.log  main;
          sendfile     on;
          tcp_nopush   on;
          server_names_hash_bucket_size 128; # this seems to be required for some vhosts
    
    
          server { # simple reverse-proxy
            listen       80;
            server_name  oxoxo.xyz;
            access_log   logs/domain2.access.log  main;
    
            location / {
              proxy_pass      http://172.21.0.15:81/;
            }
            location /wx {
              proxy_pass      http://172.21.0.15:83/;
            }
          }
    
    
        }