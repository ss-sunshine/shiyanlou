<template>
  <div>
    <swiper :options="swiperOption">
      <swiper-slide>
        <img src="static/images/jay.jpg" />
      </swiper-slide>
    </swiper>-->
    <!--以下看需要添加-->
    <!-- <div class="swiper-scrollbar"></div>//滚动条
    <div class="swiper-button-next"></div>//下一项
    <div class="swiper-button-prev"></div>//上一项
    <div class="swiper-pagination"></div>//标页码
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "",
  props: {},
  components: {},
  data() {
    return {
      swiperOption: {
        //swiper3
        autoplay: 3000,
        speed: 1000
      },
      bannerArr: []
    };
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/banner-pictures")
        .then(res => {
          // console.log(res.data);
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