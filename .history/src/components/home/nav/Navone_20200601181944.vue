<template>
  <div>
    <div class="box">
      <div class="f-j-bw">
        <div class="f-a">
          <img class="logo" src="../../../../img/9f43b00.svg" alt />
          <div class="f18">做实验, 学编程</div>
        </div>
        <div class="f-a">
          <div class="version f-a">
            <div>企业版</div>
            <div class="line"></div>
            <div>学校版</div>
          </div>
          <div>登录</div>
          <div>注册</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: {},
  components: {},
  data() {
    return {};
  },
  methods: {},
  mounted() {},
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.logo {
  width: 124px;
}
.version{
  color: #999;
  .line{
    width: 1px;
    height: 18px;
    background: #999;
    margin: 0 6px;
  }
}
</style>