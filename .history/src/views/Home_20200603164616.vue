<template>
  <div>
    <div class="container">
      <navone></navone>
    <banner></banner>
    <one></one>
    </div>
  </div>
</template>

<script>
import Navone from "../components/home/nav/Navone";
import Banner from "../components/home/banner/Banner";
import One from "../components/home/millde/One";

export default {
  name: "",
  props: {},
  components: {
    Navone,
    Banner,
    One
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