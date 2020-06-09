---
title: " kotlin Require and check\t\t"
url: 190.html
id: 190
comments: false
categories:
  - kotlin
date: 2018-07-13 20:50:21
tags:
---

Are your function arguments valid? Check before using them, with require. If they’re not valid an IllegalArgumentException is thrown. require代替check然后抛异常

    fun setName(name: String) {
      // calling setName(“”) throws IllegalArgumentException
      require(name.isNotEmpty()) { “Invalid name” }
    
      // …
    }