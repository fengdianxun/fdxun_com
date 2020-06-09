---
title: " nginx理解\t\t"
url: 150.html
id: 150
comments: false
categories:
  - nginx
date: 2018-06-19 12:56:57
tags:
---

可以写多个server监听同一个端口号，但是要求server_name不一样,就会达到虽然用的同一个主机访问不同的域名走不同的反代，达到访问不同网页的目的。 linux的nginx是一个.conf文件就是一个server，然后可以为每一个域名建一个这个配置文件，专门配置它的代理