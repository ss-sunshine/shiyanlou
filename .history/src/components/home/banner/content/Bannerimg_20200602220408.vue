<template>
  <div>
    <div class="bbb">
      <div v-for="(item) in bannerArr" :key="item.id">
        <img :src="item.mobile_picture_url" />
      </div>
    </div>

    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide v-for="(item) in bannerArr" :key="item.id">
        <img :src="item.mobile_picture_url" />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
import axios from "axios";
export default {
  name: "",
  props: {},
  components: {
    Swiper,
    SwiperSlide
  },
  data() {
    return {
      swiperOptions: {
        pagination: {
          el: ".swiper-pagination"
        }
        // Some Swiper option/callback...
      },
      bannerArr: []
    };
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/banner-pictures")
        .then(res => {
          console.log(res.data);
          this.bannerArr = res.data;
          // if (res.data.code === 200) {
          //   this.bannerArr = res.data;
          // }
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
.bbb {
  height: 100%;
  width: 880px;
  // background: rgb(255, 204, 51);
  z-index: 99;
  img {
    width: 100%;
  }
}
</style>