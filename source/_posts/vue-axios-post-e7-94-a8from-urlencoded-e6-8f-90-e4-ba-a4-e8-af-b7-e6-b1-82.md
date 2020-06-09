---
title: " vue axios post用from-urlencoded提交请求\t\t"
url: 307.html
id: 307
comments: false
categories:
  - 未分类
date: 2018-08-14 16:59:24
tags:
---

默认的axios是按照json形式提交的参数，需要引入qs类，用它转化一下.

    import axios from 'axios';
    import qs from 'qs' ;
    
    const endPoint = `${endPointApi}/ControllerX`;  
    
    const data = qs.stringify({ 
        grant_type: 'password',            
        user: userName, 
        password: userPass
    });
    
    const headers = {
        'Content-Type': 'application/x-www-form-urlencoded;charset=UTF-8'
    };
    
    axios.post(endPoint, data, headers)
    .then(function (response) {
        debugger;
        console.log(response);
    })
    .catch(function (error) {
        debugger;
        console.log(error);
    });
    

或者直接用get的拼接形式