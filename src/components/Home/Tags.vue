<template>
  <div class="header">
    <ul>
      <li v-for="i in info" :key="i.id">{{ i.content }}</li>
    </ul>
    <button class="newTags" @click="addInfo">新建标签</button>
  </div>
</template>

<script>
export default {
  name: "Tags",
  data() {
    return {
      info: [
        {id: 1, content: '衣'},
        {id: 2, content: '食'},
        {id: 3, content: '住'},
        {id: 4, content: '行'}
      ]
    }
  },
  methods: {
    addInfo() {
      this.info.push({id: 5, content: 'haha'})
    }
  }
}
</script>

<style lang='scss' scoped>
.header {
  > ul {
    display: flex;
    flex-wrap: wrap;

    > li {
      background: rgb(70, 188, 160);
      border-radius: 12px;
      padding: 2px 16px;
      margin-right: 10px;
      color: white;
      margin-bottom: 6px;
    }
  }

  > .newTags {
    margin-top: 10px;
    text-decoration: underline;
    border: none;
    background: none;
    color: rgb(70, 188, 160);
  }
}
</style>