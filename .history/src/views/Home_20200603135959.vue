<template>
  <div>
    <navone></navone>
    <banner></banner>
    <content></content>
  </div>
</template>

<script>
import Navone from "../components/home/nav/Navone";
import Banner from "../components/home/banner/Banner";
import Content from "../components/home/content/Content";
import axios from "axios";
export default {
  name: "",
  props: {},
  components: {
    Navone,
    Banner,
    Content
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