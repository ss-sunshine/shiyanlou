<template>
  <div>
      <div>
          <BannerImg :bannerArr='bannerArr'></BannerImg>
      </div>
  </div>
</template>

<script>
import axios from "axios";
import BannerImg from './content/BannerImg'
export default {
  name: "",
  props: {},
  components: {
      BannerImg
  },
  data() {
    return {
      bannerArr: []
    };
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/banner-pictures")
        .then(res => {
          console.log(res.data);
          if (res.data.code === 200) {
            this.bannerArr = res.data;
          }
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