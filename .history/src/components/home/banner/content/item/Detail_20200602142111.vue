<template>
  <div>
    <div class="title">{{itemArr.item.name}}</div>
      <div class="detail" v-for="(item,index) in itemArr" :key="index">
        
        <!-- <div class="title">{{item.tags}}</div> -->
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
}
</style>