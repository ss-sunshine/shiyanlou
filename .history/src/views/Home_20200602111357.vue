<template>
  <div>
    <div class="container">
      <div class="box">
        <navone></navone>
        <banner></banner>
      </div>
    </div>
  </div>
</template>

<script>
import Navone from "../components/home/nav/Navone";
import Banner from "../components/home/banner/Banner";
export default {
  name: "",
  props: {},
  components: {
    Navone,
    Banner
  },
  data() {
    return {};
  },
  methods: {},
  mounted() {},
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
</style>