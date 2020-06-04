<template>
  <div>
    <div class="container">
      <item class="item"></item>
      <div class="swiper-container">
        <swiper ref="mySwiper" :options="swiperOptions">
          <swiper-slide v-for="(item) in bannerArr" :key="item.id">
            <div class="BG f-j" :style="{'background':item.background_color}">
              <div class="box">
                <img :src="item.mobile_picture_url" />
              </div>
            </div>
          </swiper-slide>
          <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
          <div class="swiper-button-prev"></div>
        <div class="swiper-button-next"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Item from "../banner/content/Item";
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
import axios from "axios";
export default {
  name: "",
  props: {},
  components: {
    Item,
    Swiper,
    SwiperSlide
  },
  data() {
    return {
      swiperOptions: {
        pagination: {
          el: ".swiper-pagination",
          clickable: true
        },
        autoplay: true,
        effect: "fade",
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev"
        }
      },
      bannerArr: [],
      style: ""
    };
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/banner-pictures")
        .then(res => {
          // console.log(res.data);
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
.swiper-pagination {
  margin-left: 120px;
}
.container{
  position: relative;
}
.item {
  position: absolute;
  left: 382px;
  background: rgba(0, 0, 0, 0.1);
  height: 524PX;
  z-index: 9;
}
.BG{
  height: 524PX;
}
.box {
  img {
    width: 880px;
    margin-left: 260px;
  }
}
.swiper-container {
  position: relative;
  .swiper-button-next{
    position: absolute;
    right: 380px;
  }
  --swiper-theme-color: white; /* 设置Swiper风格 */
  --swiper-navigation-color: rgb(188, 188, 188); /* 单独设置按钮颜色 */
  --swiper-navigation-size: 30px; /* 设置按钮大小 */
}
</style>