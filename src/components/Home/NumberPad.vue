<template>
  <div class="numberPad">
    <div class="output">{{ output }}</div>
    <div class="number-buttons">
      <button @click="add('1')">1</button>
      <button @click="add('2')">2</button>
      <button @click="add('3')">3</button>
      <button @click="remove">删除</button>
      <button @click="add('4')">4</button>
      <button @click="add('5')">5</button>
      <button @click="add('6')">6</button>
      <button @click="clear">清空</button>
      <button @click="add('7')">7</button>
      <button @click="add('8')">8</button>
      <button @click="add('9')">9</button>
      <button class="ok">OK</button>
      <button class="zero" @click="add('0')">0</button>
      <button @click="add('.')">.</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "NumberPad",
  data() {
    return {
      output: '0'
    }
  },
  methods: {
    add(value) {
      if (this.output.length === 16) {
        return
      }
      if (this.output.indexOf('.') >= 0 && value === '.') {
        return;
      }
      if (this.output === '0') {
        if ('0123456789'.indexOf(value) >= 0) {
          this.output = value
        } else {
          this.output += value
        }
        return;
      }
      this.output += value
    },
    clear() {
      this.output = '0'
    },
    remove() {
      if (this.output.length === 1) {
        this.output = '0'
      } else {
        this.output = this.output.slice(0,-1)
      }

    }
  }
}
</script>

<style lang='scss' scoped>
@import "~@/assets/reset.scss";

.numberPad {
  display: flex;
  flex-direction: column;

  > .output {
    text-align: right;
    font-size: 36px;
    height: 64px;
    line-height: 64px;
    font-family: Consolas, monospace;
  }

  > .number-buttons {
    @extend %clearfix;

    > button {
      width: 25%;
      height: 52px;
      background: transparent;
      border: none;
      float: left;

      &.ok {
        height: 52*2px;
        float: right;
      }

      &.zero {
        width: 50%;
      }

      $bg: #f2f2f2;

      &:nth-child(1) {
        background: $bg;
      }

      &:nth-child(2), &:nth-child(5) {
        background: darken($bg, 4%);
      }

      &:nth-child(3), &:nth-child(6), &:nth-child(9) {
        background: darken($bg, 4*2%);
      }

      &:nth-child(4), &:nth-child(7), &:nth-child(10) {
        background: darken($bg, 4*3%);
      }

      &:nth-child(8), &:nth-child(11), &:nth-child(13) {
        background: darken($bg, 4*4%);
      }

      &:nth-child(14) {
        background: darken($bg, 4*5%);
      }

      &:nth-child(12) {
        background: rgb(70, 188, 160)
      }
    }
  }
}

</style>