---
title: " 接收500以上的statuscode\t\t"
url: 237.html
id: 237
comments: false
categories:
  - java web
date: 2018-07-17 09:41:37
tags:
---

retrofit
--------

错误内容在errorBody里，用string()取出json字符串，解析json，得到status字段的值。

    fun <T> Response<T>.status(): Int {
        return if (this.code() < 500 || this.errorBody() == null) {
            this.code()
        } else {
            val error = this.errorBody()!!.string()
            val jsonObject = JSONObject(error)
            jsonObject.getInt("status")
        }
    }
    

jquery
------

error方法返回的xhr.responseJSON是错误的返回实体,xhr.responseJSON.status就是自定义的状态码

    $.post(url, data, function (result) {}).error(function (xhr) {
            xhr.responseJSON.status
            xhr.responseJSON.message
            });