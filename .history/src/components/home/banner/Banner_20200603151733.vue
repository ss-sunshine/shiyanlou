<template>
  <div>
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide v-for="(item) in bannerArr" :key="item.id">
        <div class="container" :style="{'background':item.background_color}">
          <div class="box d-f">
            <item class="item"></item>
            <div class="swiper-container banner">
              <div>
                <img :src="item.mobile_picture_url" />
              </div>
              <div class="swiper-button-prev"></div>
              <div class="swiper-button-next"></div>
            </div>
          </div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
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
.box {
  height: 524px;
}
.swiper-pagination {
  margin-left: 100px;
}
.item {
  background: rgba(0, 0, 0, 0.1);
  z-index: 9;
}
.banner {
  height: 100%;
  width: 880px;
  img {
    width: 100%;
  }
}
.swiper-container {
  --swiper-theme-color: white; /* 设置Swiper风格 */
  --swiper-navigation-color: rgb(188, 188, 188); /* 单独设置按钮颜色 */
  --swiper-navigation-size: 30px; /* 设置按钮大小 */
}
</style>