<template>
 <div>
     <swiper :options="swiperOption">
      <swiper-slide><img src="static/images/jay.jpg"></swiper-slide>
      <swiper-slide><img src="static/images/jay.jpg"></swiper-slide>
      <swiper-slide><img src="static/images/jay.jpg"></swiper-slide>
      <swiper-slide><img src="static/images/jay.jpg"></swiper-slide>
      <swiper-slide><img src="static/images/jay.jpg"></swiper-slide>
      <swiper-slide><img src="static/images/jay.jpg"></swiper-slide>
    </swiper>
    <!--以下看需要添加-->
    <div class="swiper-scrollbar"></div> //滚动条
    <div class="swiper-button-next"></div> //下一项
    <div class="swiper-button-prev"></div> //上一项
    <div class="swiper-pagination"></div> //标页码
 </div>
</template>

<script>
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {

     }
   },
   methods: {

   },
   mounted() {

   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>

</style>