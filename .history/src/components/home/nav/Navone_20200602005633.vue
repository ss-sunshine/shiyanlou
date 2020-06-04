<template>
  <div>
    <div class="box">
      <top></top>
      <bottom></bottom>
    </div>
  </div>
</template>

<script>
import Top from './navone/Top'
import Bottom from './navone/Bottom'
export default {
  name: "",
  props: {},
  components: {
    Top,
    Bottom
  },
  data() {
    return {
      flag: false
    };
  },
  methods: {
    mouseenter() {
      this.flag = true;
    },
    mouseleave() {
      this.flag = false;
    }
  },
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
.bottom {
  background: white;
  .title {
    padding: 20px 18px;
    background: rgb(8, 191, 145);
    width: 224px;
  }
  .title-item {
    padding: 20px 18px;
    &:hover {
      color: rgb(65, 179, 150);
      cursor: pointer;
    }
    .hot {
      right: -10px;
      top: 10px;
    }
    .drop-down {
      width: 150px;
      background: white;
      top: 61px;
      left: 0;
      border-bottom-left-radius: 10px;
      border-bottom-right-radius: 10px;
      box-shadow: 0 20px 20px rgba(0, 0, 0, 0.1);
      display: block;
      .drop-down-item {
        padding: 20px 0 20px 20px;
        color: black;
        &:hover {
          background: rgb(247, 247, 247);
          color: rgb(65, 179, 150);
        }
      }
      .drop-down-it {
        padding: 20px 0 20px 20px;
        color: black;
        border-bottom-left-radius: 10px;
        border-bottom-right-radius: 10px;
        &:hover {
          background: rgb(247, 247, 247);
          color: rgb(65, 179, 150);
        }
      }
    }
    .none {
      display: none;
    }
  }
  input {
    width: 184px;
    height: 30px;
    padding-left: 5px;
    border: 1px solid #ced4da;
    color: #495057;
    border-radius: 5px;
    outline-color: rgb(131, 223, 200);
    &:hover {
      border: 2px solid rgb(131, 223, 200);
    }
  }
  .icon-sousuo{
    padding: 5px 10px;
    &:hover {
      cursor: pointer;
    }
  }
}
</style>