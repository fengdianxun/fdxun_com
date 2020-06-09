---
title: " gitlab备份与恢复\t\t"
url: 279.html
id: 279
comments: false
categories:
  - ops
date: 2018-08-06 13:08:04
tags:
---

### 备份

默认路径:/var/opt/gitlab/backups

    sudo gitlab-rake gitlab:backup:create STRATEGY=copy
    

### 恢复

    #会自动加上_gitlab_backup.tar后缀
    
    gitlab-rake gitlab:backup:restore RAILS_ENV=production BACKUP=1534392389_2018_08_15_10.7.0 
    

#### 更新配置

    gitlab-ctl reconfigure
    

### 自动备份

脚本gitlab_backup.sh

    #！ /bin/bash
    case "$1" in 
        start)
                docker exec ${容器名} gitlab-rake gitlab:backup:create
                ;;
    esac
    
    

给执行权限

    cdmod +x gitlab_backup.sh
    

执行脚本,并验证备份文件是否生成

    ./gitlab_backup.sh start
    

新增定时任务

    crontab -e
    

编辑任务内容 每天2点执行

    0 2 * * * /root/gitlab_backup.sh start
    

重新加载配置并重启服务

     systemctl reload crond
     systemctl restart crond
     ```
    
    ### 定时将备份文件上传到另一台linux服务器上
    
    安装sshpass
    
    

yum install sshpass

    脚本gitlab_upload.sh
    
    

#! /bin/bash backdir='/root/gitlab/data/backups' latestFileName=`ls $backdir -t|head -n 1` cd "$backdir" sshpass -p \[passwd\] scp "$latestFileName" root@\[hostID\]:/root/gitlab_backups ``` 后面的步骤和定时备份类型