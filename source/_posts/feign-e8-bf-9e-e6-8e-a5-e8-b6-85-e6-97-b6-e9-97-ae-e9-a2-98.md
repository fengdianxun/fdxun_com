---
title: " feign连接超时问题\t\t"
url: 255.html
id: 255
comments: false
categories:
  - java web
date: 2018-07-27 16:20:01
tags:
---

springboot默认会设置熔断器，默认超时时间和ribbon一样，造成有时候会直接切断请求。 修改方法就是主动设置超时时间。

    hystrix:
      command:
        default:
          execution:
            isolation:
              thread:
                timeoutInMilliseconds: 6000
    ribbon:
      ReadTimeout: 60000
      ConnectTimeout: 60000