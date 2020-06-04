<template>
  <div>
    <div>
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
        <div class="detail p-a-l" v-if="item.flag">
          <div>{{item.name}}</div>
          <div class="d-f f-w">
            <div v-for="(item1) in item.tags" :key="item1.id">
              <div class="d-f">
                <div class="line2"></div>
                <div class="title m-lr-1">{{item1.name}}</div>
              </div>
            </div>
            <div class="d-f" v-for="(item2) in item.recommend_courses" :key="item2.id">
              <div class="title m-lr-1">{{item2.name}}</div>
            </div>
          </div>
        </div>
        <!-- <div class="detail p-a-l"> -->
        <!-- <div>后端开发</div>
          <div class="d-f" v-for="(item1) in item.tags" :key="item1.id">
            <div class="line"></div>
            <div class="title m-lr-1">{{item1.name}}</div>
        </div>-->
        <!-- <div class="d-f" v-for="(item2) in item.recommend_courses" :key="item2.id">
            <div class="title m-lr-1">{{item2.name}}</div>
        </div>-->
        <!-- </div> -->

        <!-- <detail :itemArr="itemArr" class="detail p-a-l"></detail> -->
        <div class="line1"></div>
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
  .detail {
    width: 400px;
    background: white;
    top: 0;
    left: 260px;
    .line2 {
      width: 1px;
      height: 20px;
      background: black;
    }
  }
  .line1 {
    width: 224px;
    margin-left: 18px;
    height: 1px;
    background: rgb(188, 188, 188);
  }
}
</style>