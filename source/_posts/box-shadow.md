---
title: css中box-shadow的用法
date: 2017-07-05 15:13:29
categories: "代码笔记"
tags:
    -css
---
## 语法
```css
div{
    box-shadow: h-shadow v-shadow blur spread color inset;
}
```
## 示例
```css
div{
    box-shadow: 10px 10px 5px #888888;
}
```
## 说明
`box-shadow`向框添加一个或多个阴影。该属性是由逗号分隔的阴影列表，每个阴影由 2-4 个长度值、可选的颜色值以及可选的`inset`关键词来规定。省略长度的值是 0。

|值|描述|
|-------------|-------------|
|h-shadow|必需。水平阴影的位置。允许负值。|
|v-shadow|必需。垂直阴影的位置。允许负值。|
|blur|可选。模糊距离。|
|spread|可选。阴影的尺寸。|
|color|可选。阴影的颜色。请参阅 CSS 颜色值。|
|inset|可选。将外部阴影 (outset) 改为内部阴影。|