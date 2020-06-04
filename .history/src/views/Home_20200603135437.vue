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
import Centent from "../components/home/content/Center";
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