<template>

  <div class="tab-bar-item" @click="check">
    <div v-if="isActive"><slot name="item-icon-active"></slot></div>
    <div v-else><slot name="item-icon"></slot></div>
    <div :style="activeColor"><slot name="item-text"></slot></div>
  </div>
  
</template>

<script>
export default {
  name:"TabBarItem",
  data() {
    return {
    }
  },
  props:{
    path: String,
    color:{
      type: String,
      default: "#d4237a"
    }
  },
  computed: {
    isActive(){
      return this.$route.path.indexOf(this.path) != -1
    },
    activeColor(){
      return this.isActive? {'color': this.color}: {}
    }
  },
  methods: {
    check(){
      if(this.$route.path!=this.path){
        this.$router.push(this.path)
      }
    }
  },
}
</script>

<style>
  .tab-bar-item{
    flex: 1;
    text-align: center;
    font-size: 13px;
  }
  .tab-bar-item img{
    width: 20%;
    vertical-align: middle;
    margin: 5px 0 3px;
  }
</style>