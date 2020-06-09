---
title: " kotlin let、also区别\t\t"
url: 128.html
id: 128
comments: false
categories:
  - kotlin
date: 2018-07-13 21:08:04
tags:
---

    class A {
            val b:B=null
            fun test() {
                b.let{}
                b.also{}
            }
        }
    

function

it

this

说明

let

调用者即b

所属类即A

可以自定义返回值，即最后一行代码

also

调用者即b

所属类即A

不能自定义返回值，程序自动返回this