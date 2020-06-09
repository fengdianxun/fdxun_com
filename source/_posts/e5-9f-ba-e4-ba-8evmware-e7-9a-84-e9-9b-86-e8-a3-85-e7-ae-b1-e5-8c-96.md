---
title: " 基于VMWare的集装箱化\t\t"
url: 133.html
id: 133
comments: false
categories:
  - docker
date: 2018-06-16 16:29:23
tags:
---

vmware workstation可以导出vof格式的文件，该文件可以像docker一样，快速移植到其他装了vmware上机器上。通过简单的导入导出功能就能实现，导出时需要要求服务时开启的，并且需要导出的虚拟机处于关机状态。它会直接把所有的已经安装好的程序打包。换电脑部署时就不需要再装一遍这些软件和配置了，唯一的问题就是包会很大，因为包含的整个操作系统。导入就是打开ovf文件,后期还是建议改成docker的形式做。