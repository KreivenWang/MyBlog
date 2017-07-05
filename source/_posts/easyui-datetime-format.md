---
title: EasyUI中DateBox、DateTimeBox的格式问题
date: 2017-07-04 14:20:18
categories: "代码笔记"
tags:
    - EasyUI
---
## 问题描述
以`DateBox`为例，当属性值的格式日期分隔符为`-`，如`yyyy-MM-dd`，而`DateBox`的默认格式为`yyyy/MM/dd`时，会导致`DateBox`无法赋值，此时将显示为当前时间，而不是对应的属性值。

## 解决办法
引入`'easyui/locale/easyui-lang-zh_CN.js'`，会把日期控件的默认格式改为`'yyyy-MM-dd'`。