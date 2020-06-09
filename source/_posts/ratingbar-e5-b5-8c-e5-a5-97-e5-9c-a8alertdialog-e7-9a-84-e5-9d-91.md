---
title: " ratingbar嵌套在alertdialog的坑\t\t"
url: 303.html
id: 303
comments: false
categories:
  - android
date: 2018-08-11 20:39:23
tags:
---

通过new ratingbar的形式创建的对话框，虽然也能显示，但是不能精确控制星星的数量，需要把它在xml里定义，然后再inflate进来。

        View ratingBar = getLayoutInflater().inflate(R.layout.dialog_rate,null);
    
        new AlertDialog.Builder(this).setTitle("温馨提示").setMessage("你对这单如何评价?")
                .setView(ratingBar,16,0,16,0)
                .setPositiveButton("确定", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                        //TODO ...
    
                    }
                }).setNegativeButton("取消", null).show();