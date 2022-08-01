<template>
  <div class="header">
    <ul>
      <li v-for="item in dataSource" :key="item" @click="toggle(item)"
      :class="{selected:selectedTags.indexOf(item)>=0}">{{ item }}</li>
    </ul>
    <button class="newTags" @click="create">新建标签</button>
  </div>
</template>

<script>
export default {
  name: "Tags",
  props: ['dataSource'],
  data() {
    return {
      selectedTags: []
    }
  },
  methods: {
    create(){
      const  name = window.prompt('请输入标签名')
      if(name ===''){
        window.alert('标签名不能为空')
      }else {
        this.$emit('update:dataSource',[...this.dataSource,name])
      }
    },
    toggle(item){
      const items = this.selectedTags.indexOf(item)
      if(items>=0){
        this.selectedTags.splice(items,1)
      }else {
        this.selectedTags.push(item)
      }

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
      $bg:rgb(70, 188, 160);
      background: $bg;
      border-radius: 12px;
      padding: 2px 16px;
      margin-right: 10px;
      color: white;
      margin-bottom: 6px;
      &.selected {
        background: darken($bg,30%);
      }
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