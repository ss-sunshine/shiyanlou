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
          <div class="login">登录</div>
          <div class="registered">注册</div>
        </div>
      </div>
      <div class="f-j-bw">
        <div class="d-f f16">
        <div class="title f-color-w">全部课程</div>
        <div class>路径</div>
        <div class>训练营</div>
        <div class>楼+</div>
        <div class>
          会员
          <img src="../../../../img/02a4001.svg" alt />
        </div>
        <div class>全部课程</div>
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
.f-j-bw {
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
</style>