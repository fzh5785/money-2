<template>
  <div class="buttons">
    <ul>
      <li :class="{selected: type==='-'}" @click="selectType('-')">支出</li>
      <li :class="{selected: type==='+'}" @click="selectType('+')">收入</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Buttons",
  data() {
    return {
      type:'-'
    }
  },
  methods: {
    selectType(type){
      this.type = type
    }
  }
}
</script>

<style lang='scss' scoped>
.buttons {
  height: 40px;

  > ul {
    display: flex;
    width: 100%;
    height: 40px;
    line-height: 40px;

    > li {
      width: 50%;
      background: rgb(243, 243, 243);
      font-size: 16px;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;

      &.selected::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        border-bottom: 3px solid #333;
      }
    }
  }

}
</style>