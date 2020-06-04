<template>
  <div>
    <div class="box">
      <div class="top f-j-bw">
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
          <div class="login">登录</div>
          <div class="registered">注册</div>
        </div>
      </div>
      <div class="bottom f-j-bw">
        <div class="f-a f16">
          <div class="title f-color-w">全部课程</div>
          <div class="title-item">路径</div>
          <div class="title-item">训练营</div>
          <div class="title-item">楼+</div>
          <div class="title-item p-r">
            会员
            <img src="../../../../img/02a4001.svg" class="hot p-a-t" />
          </div>
          <div class="title-item">社区</div>
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
.top {
  margin: 15px 0 20px;
  .logo {
    width: 124px;
  }
  .version {
    color: #999;
    .line {
      width: 1px;
      height: 15px;
      background: #999;
      margin: 0 6px;
    }
  }
  .login {
    padding: 12px 26px;
    color: rgb(8, 191, 145);
    &:hover {
      cursor: pointer;
      color: #057659;
    }
  }
  .registered {
    background: rgb(8, 191, 145);
    color: white;
    padding: 12px 26px;
    &:hover {
      cursor: pointer;
    }
  }
}
.title {
  padding: 20px 18px;
  background: rgb(8, 191, 145);
  width: 224px;
}
.title-item{
  padding: 20px 18px;
}
.hot{
  right: -10px;
  top: 10px;
}
</style>