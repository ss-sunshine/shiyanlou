<template>
  <div>
    <div class="itemArr p-r" v-for="(item,index) in itemArr" :key="index">
      <div class="">
        <div class="Arr-item f16 f-a">
          <div class="item-name m-r-1">{{item.name}}</div>
          <div class="item-name m-r-1 f14">{{item.tags[0].name}}</div>
          <div class="item-name m-r-1 f14">{{item.tags[1].name}}</div>
        </div>
       
        <div class="line"></div>
      </div>
    </div>
     <detail :itemArr="itemArr" class="detail p-a-l"></detail>
  </div>
</template>

<script>
import axios from "axios";
import Detail from "./item/Detail";
export default {
  name: "",
  props: {},
  components: {
    Detail
  },
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
    padding: 18px 0 18px 18px;
    color: white;
    &:hover {
      background: white;
      color: black;
    }
    .item-name {
      &:hover {
        color: rgb(8, 191, 145);
        cursor: pointer;
      }
    }
  }
  
  .line {
    width: 224px;
    margin-left: 18px;
    height: 1px;
    background: rgb(188, 188, 188);
  }
}
.detail {
    left: 260px;
    top: 0;
  }
</style>