---
title: " gradle-docker插件使用\t\t"
url: 277.html
id: 277
comments: false
categories:
  - 未分类
date: 2018-08-02 17:32:20
tags:
---

[插件地址](https://github.com/palantir/gradle-docker "插件地址") files的意思是把一些文件或者文件夹指定到docker打镜像的上下文里

    version = '1.0.0'
    docker {
        name "${war.baseName}:${war.version}"
        files 'default.conf','src/main' //指定docker打包上线文里的文件
    }
    

### 打镜像

    gradle docker
    

相当于运行下面的指令，只不过不用手动输入项目名和版本号

    docker build -t 项目名:version .