<template>
  <div class='home'>
    <Layout layout="wrapper">
      <NumberPad/>
      <Buttons/>
      <Notes/>
      <Tags :data-source.sync="tags"/>
    </Layout>
  </div>
</template>

<script>

import NumberPad from "@/components/Home/NumberPad";
import Notes from "@/components/Home/Notes";
import Buttons from "@/components/Home/Buttons";
import Tags from "@/components/Home/Tags";

export default {
  name: "Home",
  components: {Tags, Buttons, Notes, NumberPad},
  data() {
    return {
      tags: ['衣','食','住','行']
    }
  },
  methods: {}
}
</script>

<style scoped lang='scss'>
@import "~@/assets/reset.scss";

::v-deep .wrapper > .content {
  display: flex;
  flex-direction: column-reverse;
}


</style>