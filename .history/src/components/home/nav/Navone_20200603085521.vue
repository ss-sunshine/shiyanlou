<template>
  <div>
    <div class="container">
      <div class="box">
      <top></top>
      <bottom class="bottom"></bottom>
    </div>
    </div>
  </div>
</template>

<script>
import Top from './navone/Top'
import Bottom from './navone/Bottom'
export default {
  name: "",
  props: {},
  components: {
    Top,
    Bottom
  },
  data() {
    return {
    };
  },
  methods: {
  },
  mounted() {},
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.bottom{
  z-index: 99999;
}
</style>