---
title: " frp内网透传http服务\t\t"
url: 110.html
id: 110
comments: false
categories:
  - 内网透传
date: 2018-06-13 10:56:57
tags:
---

`vi frps.ini`

    [common]
    bind_port = 7000
    vhost_http_port = 80
    dashboard_port = 7500
    dashboard_user = user
    dashboard_pwd = password
    subdomain_host = nat.fdxun.com
    token = "xxxxxxxxx"
    

`vi frpc.ini`

    [common]
    server_addr = nat.fdxun.com
    server_port = 7000
    
    [web]
    type = http
    local_port = 8080
    use_encryption = true
    use_compression =true
    token = "xxxxxxxxx"
    subdomain = test
    

注意： 1\. http透传时只能是域名形式，不能是ip地址形式 2. 域名支持3级，即xxx.nat.fdxun.com