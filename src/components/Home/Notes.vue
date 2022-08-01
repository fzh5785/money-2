<template>
  <div class="notes">
    <label>
      <span>备注</span>
      <input type="text" placeholder="在这里输入备注" v-model="value">
    </label>
  </div>
</template>

<script>
export default {
  name: "Notes",
  data() {
    return {
      value : ''
    }
  },
  methods: {}
}
</script>

<style lang='scss' scoped>
.notes {
  width: 100%;
  height: 40px;

  > label {
    display: flex;
    justify-content: center;
    align-items: center;

    > span {
      margin-right: 10px;
    }

    > input {
      flex-grow: 1;
      border: none;
      height: 40px;
    }
  }
}
</style>