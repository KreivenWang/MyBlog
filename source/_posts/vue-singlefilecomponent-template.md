---
title: Vue单文件组件模板
---
>**说明：**Vue单文件组件的模板，包含template/script/style的基本结构。配合**Eslint**，缩进为2个空格，加入scss。

```
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