<template>
  <div>
    <div class="bbb"></div>
    <!-- <div v-for="(item) in bannerArr" :key="item.id">
      <img :src="item.mobile_picture_url" />
    </div> -->
    <!-- <swiper 
    :options="swiperOption" 
    v-for="(item) in bannerArr" 
    :key="item.id"
    >
      <swiper-slide>
        <img :src="item.mobile_picture_url" />
      </swiper-slide>
    </swiper> -->
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'
import axios from "axios";
export default {
  name: "",
  props: {
  },
  components: {
    Swiper,
    SwiperSlide
  },
  data() {
    return {
      // swiperOption: {
      //   //swiper3
      //   autoplay: 3000,
      //   speed: 1000
      // },
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
.bbb{
  width: 880px;
  background: rgb(255,204,51);
}
</style>