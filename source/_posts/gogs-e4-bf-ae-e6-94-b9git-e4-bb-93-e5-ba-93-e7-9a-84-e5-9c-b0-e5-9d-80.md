---
title: " gogs修改git仓库的地址\t\t"
url: 172.html
id: 172
comments: false
categories:
  - git
date: 2018-06-23 20:44:13
tags:
---

当我们用docker部署后，仓库地址默认会用localhost地址。而我们实际访问的应该是个域名，需要手动修改。 1. 安装之前需要把gogs的data目录映射到宿主机，因为要修改配置文件。 2. 配置文件在 /conf/app.ini 3. 修改server标签下的ROOT_URL 为外网地址