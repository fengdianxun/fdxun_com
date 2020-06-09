---
title: " android TextClock\t\t"
url: 382.html
id: 382
comments: false
categories:
  - 未分类
date: 2018-10-08 13:46:38
tags:
---

从Android 4.2开始增加了TextClock组件，继承自TextView。用途是动态数字时钟。自动识别系统的时间是12小时制还是24小时制，根据设置的格式显示。不需要程序内自己做线程或者延时迭代实现，最省力。

     <TextClock
                    android:id="@+id/timeTc"
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="bottom"
                    android:format24Hour="yyyy年MM月dd日 HH:mm:ss"
                    android:format12Hour="yyyy年MM月dd日 hh:mm:ss"
                    android:text="2018年07月02日 10:00:00"
                    android:textColor="#010110"
                    android:textSize="18sp" />
    

如果不想根据系统的12小时制或者24小时制走，可以在设置格式化格式的时候都设置成一种格式，比如24小时制，就可以format24Hour和format12Hour都用yyyy年MM月dd日 HH:mm:ss格式