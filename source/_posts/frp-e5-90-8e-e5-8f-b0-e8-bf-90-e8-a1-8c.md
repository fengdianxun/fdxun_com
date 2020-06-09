---
title: " frp后台运行\t\t"
url: 87.html
id: 87
comments: false
categories:
  - 内网透传
date: 2018-06-09 18:37:23
tags:
---

`vi /etc/systemd/system/frps.service` 新建此文件，并写入以下内容

    [Unit]
    Description=frps daemon
    After=syslog.target  network.target
    Wants=network.target
    
    [Service]
    Type=simple
    ExecStart=/usr/sbin/frp/frps -c /etc/frp/frps.ini
    Restart= always
    RestartSec=1min
    ExecStop=/usr/bin/killall frps
    
    
    [Install]
    WantedBy=multi-user.target
    

启动并设为开机自启。 `systemctl start frps` `systemctl enable frps`