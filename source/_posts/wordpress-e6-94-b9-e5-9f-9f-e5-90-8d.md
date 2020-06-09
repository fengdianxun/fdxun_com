---
title: " wordpress改域名\t\t"
url: 121.html
id: 121
comments: false
categories:
  - 未分类
date: 2018-06-13 14:29:23
tags:
---

        UPDATE wp_options SET option_value = replace(option_value, 'www.mydomain.com','www.newdomain.com') ;
        UPDATE wp_posts SET post_content = replace(post_content, 'www.mydomain.com','www.newdomain.com') ;
        UPDATE wp_comments SET comment_content = replace(comment_content, 'www.mydomain.com', 'www.newdomain.com') ;
        UPDATE wp_comments SET comment_author_url = replace(comment_author_url, 'www.mydomain.com', 'www.newdomain.com') ;