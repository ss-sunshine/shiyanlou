<template>
  <div>
    <!-- <div class="banner"></div> -->
    <swiper 
    :options="swiperOption" 
    v-for="(item,index) in bannerArr" 
    :key="index"
    >
      <swiper-slide>
        <img :src="item.picture_url" />
      </swiper-slide>
    </swiper>
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
.banner{
  width: 100%;
  height: 515px;
  background: rgb(255,204,51);
}
</style>