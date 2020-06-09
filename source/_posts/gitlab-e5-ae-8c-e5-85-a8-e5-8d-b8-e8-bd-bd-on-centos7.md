---
title: " gitlab 完全卸载 on centos7\t\t"
url: 312.html
id: 312
comments: false
categories:
  - 未分类
date: 2018-08-17 08:59:57
tags:
---

    sudo gitlab-ctl stop
    sudo yum remove gitlab-ce
    sudo rm -r /var/opt/gitlab
    sudo rm -r /opt/gitlab
    sudo rm -r /etc/gitlab