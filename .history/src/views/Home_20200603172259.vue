<template>
  <div>
    <navone></navone>
    <banner></banner>
    <one></one>
    <Two>
      <template v-slot:clssify>
        <div v-if=""></div>
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
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/louplus")
        .then(res => {
          console.log(res.data);
          this.oneArr = res.data;
        })
        .catch(err => {
          console.log(err);
        });
    }
  },
  mounted() {
    this.getData();
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
</style>