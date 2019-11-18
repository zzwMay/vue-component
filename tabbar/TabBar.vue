<template>
  <div id="tab-bar">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name:"TabBar"
}
</script>

<style lang="less">
#tab-bar{
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 49px;
  background-color: #f6f6f6;
  box-shadow: 0 -1px 1px rgba(240, 240, 240, 0.8);
  display: flex;
}

</style>