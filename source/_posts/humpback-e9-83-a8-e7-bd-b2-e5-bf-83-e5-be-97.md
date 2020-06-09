---
title: " humpback部署心得\t\t"
url: 217.html
id: 217
comments: false
categories:
  - docker
date: 2018-07-13 15:11:52
tags:
---

[humpback官方教程](https://humpback.github.io/humpback/#/zh-cn/humpback-arch "humpback官方教程")

1.  如果不用集群可以只部署humpback-web和humpback-agent。
2.  humpback-web是管理平台，自己没有数据，依赖humpback-agent提供数据
3.  humpback-web安传统教程部署就可以了
4.  humpback-agent要注意它说的-v是必须要加的，要不这个服务没有权限操作一些东西,agent部署成host网络
5.  部署私有仓库时要用-v把配置文件对应出来，因为要加一些参数支持跨域请求