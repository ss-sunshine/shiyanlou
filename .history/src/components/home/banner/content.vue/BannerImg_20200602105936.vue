<template>
  <div>
      <div>
        {{bannerArr.item}}
      </div>
    <!-- <swiper 
    :options="swiperOption" 
    v-for="(item,index) in bannerArr" 
    :key="index"
    >
      <swiper-slide>
        <img :src="item.picture_url" />
      </swiper-slide>
    </swiper> -->
    <!--以下看需要添加-->
    <!-- 滚动条 -->
    <!-- <div class="swiper-scrollbar"></div> -->
    <!-- 下一项 -->
    <!-- <div class="swiper-button-next"></div> -->
    <!-- 上一项 -->
    <!-- <div class="swiper-button-prev"></div> -->
    <!-- 标页码 -->
    <!-- <div class="swiper-pagination"></div> -->
  </div>
</template>

<script>
export default {
  name: "",
  props: {
    bannerArr:{
      type:Array
    }
  },
  components: {},
  data() {
    return {
      swiperOption: {
        //swiper3
        autoplay: 3000,
        speed: 1000
      }
    };
  },
  methods: {
  },
  mounted() {
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
</style>