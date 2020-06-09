---
title: " feign加logs日志\t\t"
url: 291.html
id: 291
comments: false
categories:
  - java web
date: 2018-08-09 14:46:29
tags:
---

新建feignconfig文件,这样的配置就可以输出全部的feign的log信息

    import feign.Logger;
    import org.springframework.context.annotation.Bean;
    import org.springframework.context.annotation.Configuration;
    
    @Configuration
    public class FeignConfig {
    
        @Bean
        public Logger.Level feignLoggerLevel() {
            return feign.Logger.Level.FULL;
        }
    }
    

配置文件引用FeignClient注解的文件，这样就可以将feign的log写入文件中

    logging:
      level:
          com:
            fdx: 
              api:
                UserService: debug