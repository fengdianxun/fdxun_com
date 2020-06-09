---
title: " gitlab报500问题修复\t\t"
url: 437.html
id: 437
comments: false
categories:
  - 未分类
date: 2019-10-16 12:44:11
tags:
---

Enter the DB console: For Omnibus GitLab packages:

    sudo gitlab-rails dbconsole
    

### Reset CI/CD variables

Drop the table:

    DELETE FROM ci_group_variables;
    DELETE FROM ci_variables;
    

### Reset Runner registration tokens

    -- Clear project tokens
    UPDATE projects SET runners_token = null, runners_token_encrypted = null;
    -- Clear group tokens
    UPDATE namespaces SET runners_token = null, runners_token_encrypted = null;
    -- Clear instance tokens
    UPDATE application_settings SET runners_registration_token_encrypted = null;
    -- Clear runner tokens
    UPDATE ci_runners SET token = null, token_encrypted = null;
    

### Reset pending pipeline jobs

    -- Clear build tokens
    UPDATE ci_builds SET token = null, token_encrypted = null;
    

更新配置 gitlab-ctl reconfigure