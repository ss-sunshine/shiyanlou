<template>
  <div>
    <div class="itemArr" v-for="(item,index) in itemArr" :key="index">
      <div class="Arr-item f16 d-f">
        <div class="m-r-1 f-a">{{item.name}}</div>
        <div class="m-r-1 f12">{{item.tags[0].name}}</div>
        <div class="m-r-1 f12">{{item.tags[1].name}}</div>
      </div>
      <div class="line"></div>
    </div>
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
      itemArr: []
    };
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/categories")
        .then(res => {
          console.log(res.data);
          this.itemArr = res.data;
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
.itemArr {
  background: rgba(0, 0, 0, 0.1);
  width: 260px;
  .Arr-item {
    padding: 18px 18px;
    color: white;
    &:hover {
      background: white;
      color: black;
    }
  }
  .line {
    width: 224px;
    margin-left: 18px;
    height: 1px;
    background: rgb(188, 188, 188);
  }
}
</style>