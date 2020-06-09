---
title: " gson代替jackson的converter地位\t\t"
url: 169.html
id: 169
comments: false
categories:
  - java web
date: 2018-06-20 21:27:43
tags:
---

### 初衷

为什么会要用gson替代jackson原因如下： - jackson的序列化依赖的是getter - 首字母大写的属性在用getter序列化时会自动转换成小写，就和属性名本身不一致 - gson序列化直接依赖属性本身，名称不会变，即使加getter也不会按照getter方式序列化

### 步骤

1.  增加gson依赖

                <dependency>
                    <groupId>com.google.code.gson</groupId>
                    <artifactId>gson</artifactId>
                    <version>2.8.2</version>
                </dependency>
    

2.  增加配置文件

    package com.example.demo;
    
    import org.springframework.boot.autoconfigure.web.HttpMessageConverters;
    import org.springframework.context.annotation.Bean;
    import org.springframework.context.annotation.Configuration;
    import org.springframework.http.converter.HttpMessageConverter;
    import org.springframework.http.converter.json.GsonHttpMessageConverter;
    
    import java.util.ArrayList;
    import java.util.Collection;
    
    @Configuration
    public class GsonConfiguration {
    
        @Bean
        public HttpMessageConverters customConverters() {
            Collection<HttpMessageConverter<?>> messageConverters = new ArrayList<>();
            GsonHttpMessageConverter gsonHttpMessageConverter = new GsonHttpMessageConverter();
            messageConverters.add(gsonHttpMessageConverter);
            return new HttpMessageConverters(true, messageConverters);
        }
    }
    
    

#### 附加

如果不想要jackson就加下面的依赖忽略，如果想2个共存可以不加 ，如果共存需注意转化顺序。

            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-starter-web</artifactId>
                <exclusions>
                    <exclusion>
                        <artifactId>jackson-databind</artifactId>
                        <groupId>com.fasterxml.jackson.core</groupId>
                    </exclusion>
                </exclusions>
            </dependency>