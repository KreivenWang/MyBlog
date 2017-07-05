---
title: Vue单文件组件模板
#date: 2016-06-01 23:47:44 #文章生成時間
categories: "代码笔记" #文章分類目錄 可以省略
tags: #文章標籤 可以省略
     - Vue
description: #你對本頁的描述 可以省略
---
>**说明：**Vue单文件组件的模板，包含template/script/style的基本结构。配合**Eslint**，缩进为2个空格，加入scss。

```html
<template>
  <div>hello {{x}}</div>
</template>

<script>
export default {
  data() {
    return {
      x: 'single file component'
    };
  }
};
</script>

<style lang='scss' scoped>

</style>
```