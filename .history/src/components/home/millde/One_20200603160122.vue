<template>
  <div>
    <div class="container">
      <div class="box">
        <div class="title f-j-bw m-tb-3">
          <div class="f-a">
            <div class="f24">楼+ 实战课程</div>
            <div class="line m-lr-1"></div>
            <div class="min-title f14">定期开班, 导师助教全程辅导, 最快最优成长</div>
          </div>
          <div class="f14">更多&gt;</div>
        </div>
        <div class="f-j-bw">
          <div v-for="(item) in oneArr.slice(0,4)" :key="item.id">
            <div class="item">
              <img :src="item.picture_url" alt="">
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "",
  props: {
    // oneArr:{
    //   type:Array
    // }
  },
  components: {},
  data() {
    return {
      oneArr:[]
    };
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/louplus")
        .then(res => {
          console.log(res.data);
          this.oneArr = res.data;
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
.title {
  color: #565656;
  .line {
    width: 2px;
    height: 24px;
    background: #565656;
  }
}
.item{
  height: 180px;
}
</style>