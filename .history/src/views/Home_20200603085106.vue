<template>
  <div>
    <navone class="navone"></navone>
    <banner></banner>
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
.navone{
  z-index: 99;
}
</style>