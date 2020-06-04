<template>
  <div>
    <navone></navone>
    <banner></banner>
    <one></one>
    <Two>
      <template v-slot:clssify>

      </template>
    </Two>
  </div>
</template>

<script>
import Navone from "../components/home/nav/Navone";
import Banner from "../components/home/banner/Banner";
import One from "../components/home/millde/One";
import Two from "../components/home/millde/Two";

export default {
  name: "",
  props: {},
  components: {
    Navone,
    Banner,
    One,
    Two
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