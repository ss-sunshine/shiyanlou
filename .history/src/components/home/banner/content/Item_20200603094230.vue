<template>
  <div>
    <div class="item">
      <div
        class="itemArr p-r"
        v-for="(item,index) in itemArr"
        :key="index"
        @mouseenter="enter(item)"
        @mouseleave="leave(item)"
      >
        <div class="Arr-item f16 f-a">
          <div class="item-name m-r-1">{{item.name}}</div>
          <div class="item-name m-r-1 f14">{{item.tags[0].name}}</div>
          <div class="item-name m-r-1 f14">{{item.tags[1].name}}</div>
        </div>
        <div class="detail p-a-l f12" v-if="item.flag">
          <div class="title1 f14">{{item.name}}</div>
          <div class="l-h f-a f-w">
            <div v-for="(item1) in item.tags" :key="item1.id">
              <div class="f-a">
                <div class="line2"></div>
                <div class="m-lr-1">{{item1.name}}</div>
              </div>
            </div>
            <div class="line2"></div>
          </div>
          <div class="title2 f14">课程推荐</div>
          <div class="d-f l-h" v-for="(item2) in item.recommend_courses" :key="item2.id">
            <div class="m-lr-1">{{item2.name}}</div>
          </div>
        </div>
        <div class="line1"></div>
      </div>
      <div class="butn f-j">
        <div class="btn f14">经营专区</div>
      </div>
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
      itemArr: [],
      flag: false
    };
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/categories")
        .then(res => {
          console.log(res.data);
          res.data.map(item => {
            this.$set(item, "flag", false);
          });
          this.itemArr = res.data;
        })
        .catch(err => {
          console.log(err);
        });
    },
    enter(item) {
      item.flag = true;
    },
    leave(item) {
      item.flag = false;
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
.item{
  // background: rgba(0, 0, 0, 0.1);
  width: 260px;
  .itemArr {
  
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
  .detail {
    width: 360px;
    background: white;
    top: 0;
    left: 260px;
    color: #495057;
    padding: 18px;
    .title1 {
      background: rgb(238, 238, 238);
      width: 100px;
      margin-bottom: 18px;
      padding: 2px 6px;
    }
    .title2 {
      background: rgb(238, 238, 238);
      width: 60px;
      margin: 24px 0;
      padding: 2px 6px;
    }
    .l-h{
      line-height: 2.5;
      .line2 {
      width: 1px;
      height: 16px;
      background: #495057;
    }
    }
    
  }

  .line1 {
    width: 224px;
    margin-left: 18px;
    height: 1px;
    background: rgb(188, 188, 188);
  }
}
.butn{
  // padding: 18px 0;
  // background: rgba(0, 0, 0, 0.1);
  .btn{
  padding: 4px 20px;
  border: 1px solid white;
  border-radius: 25px;
  color: white;
  &:hover{
    color: black;
    background: white;
    cursor: pointer;
  }
}
}
}

</style>