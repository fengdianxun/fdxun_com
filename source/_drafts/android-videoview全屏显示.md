---
title: " android videoview全屏显示\t\t"
url: 418.html
id: 418
comments: false
categories:
  - 未分类
tags:
---

videoview的宽高设置成match\_parent并不能保证内容全屏显示，只会显示在左上方。 外层包裹LinearLayout也是没有效果的，必须要包裹RelativeLayout，并且要指定layout\_alignParentTop、layout\_alignParentBottom、layout\_alignParentLeft、layout_alignParentRight。