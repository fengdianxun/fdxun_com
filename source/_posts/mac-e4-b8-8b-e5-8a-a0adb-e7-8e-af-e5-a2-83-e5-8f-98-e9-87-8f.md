---
title: " mac下加adb环境变量\t\t"
url: 185.html
id: 185
comments: false
categories:
  - android
date: 2018-07-13 20:51:52
tags:
---

1、终端中输入 cd ~ 回车 2、输入 touch .bash\_profile 回车 touch：如果没有，则创建文件；如果有，更新一下文件时间 3、输入open -e .bash\_profile 回车 open：打开文件 4、在打开的文件最后加入以下内容： export PATH=/Users/wangduo/Library/Android/sdk/platform-tools/:${PATH} 5、终端中输入 source .bash_profile