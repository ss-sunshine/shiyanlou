<template>
  <div>
    <swiper 
    :options="swiperOption" 
    v-for="(item,index) in bannerArr" 
    :key="index"
    >
      <div>
        <img :src="item.picture_url" />
      </div>
    </swiper>
    <!--以下看需要添加-->
    <!-- 滚动条 -->
    <div class="swiper-scrollbar"></div>
    <!-- 下一项 -->
    <div class="swiper-button-next"></div>
    <!-- 上一项 -->
    <div class="swiper-button-prev"></div>
    <!-- 标页码 -->
    <div class="swiper-pagination"></div>
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