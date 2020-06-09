---
title: " gradle 打包 oneJar\t\t"
url: 352.html
id: 352
comments: false
categories:
  - 未分类
date: 2018-08-28 15:42:18
tags:
---

    jar {
        from {
            configurations.compile.collect { it.isDirectory() ? it : zipTree(it) }
        }
        manifest {
            attributes 'Main-Class': 'com.fdxun.Main'
        }
    }
    

如果需要把src里的不是java文件也打包进去，比如hbm.xml文件，加下面代码

    //将src文件夹中的资源文件同时打包
    processResources {
        from('src') {
            include '**/*.hbm.xml'
        }
    }