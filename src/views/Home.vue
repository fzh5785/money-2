<template>
  <div class='home'>
    <Layout layout="wrapper">
      <NumberPad/>
      <Buttons/>
      <Notes/>
      <Tags/>
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
    return {}
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