<template>
  <div>
    <div class="container">
      <div class="box">
        <div class="title f-j-bw m-tb-3">
          <div class="f-a">
            <div class="f24">
              <slot name="clssify"></slot>
            </div>
            <div class="line m-lr-1"></div>
            <div class="min-title f14">
              <slot name="desc"></slot>
            </div>
          </div>
          <div class="f14">更多&gt;</div>
        </div>
        <div class="f-j-bw">
          <div v-for="(item) in titleArr" :key="item.id">
            <div class="f-j-bw">
                <div v-for="(item) in item.courses.slice(8,12)" :key="item.id">
              <div class="item">
                <img :src="item.picture_url" alt />
                <div class="m-t-15 p-lr-1">
                  <div class="item1 f18">{{item.title}}</div>
                  <div class="item2 f16">最近班: {{item.open_time}}</div>
                </div>
              </div>
            </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: {
    titleArr: {
      type: Array
    }
  },
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
.title {
  color: #565656;
  .line {
    width: 2px;
    height: 24px;
    background: #565656;
  }
}
.item {
  height: 180px;
  background: white;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.2);
  &:hover {
    box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.2);
  }
  img {
    height: 150px;
  }
  .item1 {
    margin-bottom: 6px;
    color: #565656;
  }
  .item2 {
    color: #a4a4a4;
  }
}
</style>