---
title: " ADB 指令\t\t"
url: 434.html
id: 434
comments: false
categories:
  - 未分类
date: 2019-10-15 09:12:05
tags:
---

停止应用

    adb shell am force-stop ${applicationId}
    

打开设置

    adb shell am start -a android.settings.SETTINGS
    

拉取文件

    adb pull /sdcard/xxx/ .
    

打开应用

    adb shell am start -n "${applicationId}/${带包名的Activity}" -a android.intent.action.MAIN -c android.intent.category.LAUNCHER
    

拉取系统日志

    adb logcat > log.txt
    

卸载应用并保留数据

    adb shell pm uninstall -k ${包名}
    

替换安装

    adb install -r ${文件路径}
    

相关链接 [玩转ADB命令（ADB命令使用大全）](https://blog.csdn.net/zhonglunshun/article/details/78362439 " 玩转ADB命令（ADB命令使用大全）")