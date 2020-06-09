---
title: " jetpack navigation BottomNavigationView不切换可能的坑\t\t"
url: 391.html
id: 391
comments: false
categories:
  - 未分类
date: 2018-11-19 16:45:38
tags:
---

**navigation文件里定义的item要能在nav.xml里有对应**

        <com.google.android.material.bottomnavigation.BottomNavigationView
                android:id="@+id/navigation"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:background="?android:attr/windowBackground"
                app:menu="@menu/navigation"/>
    

navigation.xml

    <?xml version="1.0" encoding="utf-8"?>
    <menu xmlns:android="http://schemas.android.com/apk/res/android">
    
        <item
                android:id="@+id/missionFragment"
                android:icon="@drawable/ic_home_black_24dp"
                android:title="任务"/>
    
        <item
                android:id="@+id/readFragment"
                android:icon="@drawable/ic_dashboard_black_24dp"
                android:title="读卡"/>
    
    </menu>
    

nav.xml

        <?xml version="1.0" encoding="utf-8"?>
        <navigation xmlns:android="http://schemas.android.com/apk/res/android"
                    xmlns:app="http://schemas.android.com/apk/res-auto"
                    xmlns:tools="http://schemas.android.com/tools" android:id="@+id/navi_graph"
                    app:startDestination="@id/missionFragment">
    
            <fragment android:id="@+id/missionFragment" android:name="cn.com.gmcc.sign.fragment.MissionFragment"
                      android:label="任务列表" tools:layout="@layout/fragment_mission">
            </fragment>
            <fragment android:id="@+id/readFragment" android:name="cn.com.gmcc.sign.fragment.ReadFragment"
                      android:label="读卡" tools:layout="@layout/fragment_read"></fragment>
        </navigation>