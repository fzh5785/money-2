<template>
  <div class='Layout'>
    <div class="wrapper">
      <div class="content" :class="layout">
        <slot/>
      </div>
      <Nav/>
    </div>
  </div>
</template>

<script>
import Nav from "@/components/Nav";

export default {
  name: "Layout",
  components: {Nav},
  data() {
    return {}
  },
  props: ['layout'],
  methods: {}
}
</script>

<style scoped lang='scss'>
.wrapper {
  display: flex;
  flex-direction: column;
  height: 100vh;

  > .content {
    flex-grow: 1;
    overflow: auto;
  }
}

</style>