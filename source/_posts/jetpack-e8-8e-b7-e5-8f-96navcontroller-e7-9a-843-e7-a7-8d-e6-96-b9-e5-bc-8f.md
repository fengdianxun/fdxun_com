---
title: " jetpack 获取NavController的3种方式\t\t"
url: 394.html
id: 394
comments: false
categories:
  - 未分类
date: 2018-11-19 17:03:25
tags:
---

jetpack里建议ui用fragment组建，但是不像传统的方式自行管理fragment的示例，采用和activity类似的思想，托管给框架，注册给nav.xml，通过NavController来控制fragment，主要是控制跳转。 navigation有2种依赖包 - 基本

        implementation "android.arch.navigation:navigation-fragment:1.0.0-alpha07"
        implementation "android.arch.navigation:navigation-ui:1.0.0-alpha07"
    

*   KTX

        implementation "android.arch.navigation:navigation-fragment-ktx:1.0.0-alpha07"
        implementation "android.arch.navigation:navigation-ui-ktx:1.0.0-alpha07"
    

获取方式也自然分2种

*   基本

通过activity获取 Navigation.java

    public static NavController findNavController(@NonNull Activity activity, @IdRes int viewId) 
    

通过view获取 Navigation.java

    public static NavController findNavController(@NonNull View view)
    

通过Fragment获取 NavHostFragment.java public static NavController findNavController(@NonNull Fragment fragment) - KTX 通过activity获取

    fun Activity.findNavController(@IdRes viewId: Int): NavController
    

通过view获取

    fun View.findNavController(): NavController
    

通过Fragment获取

    fun Fragment.findNavController(): NavController