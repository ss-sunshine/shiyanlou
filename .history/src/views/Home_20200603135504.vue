<template>
  <div>
    <navone></navone>
    <banner></banner>
    <center></center>
  </div>
</template>

<script>
import Navone from "../components/home/nav/Navone";
import Banner from "../components/home/banner/Banner";
import Content from "../components/home/content/Content";
export default {
  name: "",
  props: {},
  components: {
    Navone,
    Banner,
    Center
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