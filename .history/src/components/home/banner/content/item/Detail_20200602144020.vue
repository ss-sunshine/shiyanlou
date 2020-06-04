<template>
  <div>
      <div class="detail" v-for="(item,index) in itemArr" :key="index">
        <div class="title">{{item.name}}</div>
        <div>
          <div class="line"></div>
          <div class="title">{{item.tags.name}}</div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: {
    itemArr:{
      type:Array
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
.detail{
  width: 400px;
  background: white;
  .line{
    width: 1px;
    height: 20px;
    background: black;
  }
}
</style>