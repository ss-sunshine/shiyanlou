<template>
  <div>
      <div class="details" v-for="(item,index) in itemArr" :key="index">
        <div class="title">{{item.name}}</div>
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
.details{
  width: 400px;
  background: white;
}
</style>