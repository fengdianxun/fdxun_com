---
title: " kotlin奇技淫巧\t\t"
url: 30.html
id: 30
comments: false
categories:
  - kotlin
date: 2018-07-13 21:18:20
tags:
---

### 一个list转化成另一个list

                val newlist = list.flatMap {
                    listOf(RemoteBanner(it))
                }
    

it表示迭代器的每一个元素

### 从集合里根据条件查找第一个结果元素

返回第一个匹配到的元素

    list.find { it.key == key }