<template>
  <div :style="{background, color}" class="my-header">{{ name }}</div>
</template>

<script>
export default {
  props: {
    name: String,
    background: {
      type: String,
      default: 'green'
    },
    color: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="less" scoped>
.my-header {
  height: 45px;
  line-height: 45px;
  text-align: center;
  background-color: #1d7bff;
  color: #fff;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 2;
}
</style>
