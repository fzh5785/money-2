<template>
  <div class='Nav'>
    <router-link to="/home" class="item" active-class="selected">
      <i class="iconfont icon-moneybag"></i>
      首页
    </router-link>
    <router-link to="/labels" class="item" active-class="selected">
      <i class="iconfont icon-labels"></i>
      标签
    </router-link>
    <router-link to="/count" class="item" active-class="selected">
      <i class="iconfont icon-tongji"></i>
      统计
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Nav",
  data() {
    return {}
  },
  methods: {}
}
</script>

<style scoped lang='scss'>
.Nav {
  display: flex;
  background: rgb(70, 188, 160);
  >.item {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 33.33%;
    text-decoration: none;
    padding: 5px 0;
    color: white;
    position: relative;
  }
  .item.selected{
    font-weight: 700;
  }
  .item.selected::after{
    content: '';
    width: 33.33%;
    height: 3px;
    clear: both;
    top: 0;
    background: white;
    position: absolute;
  }
}
</style>