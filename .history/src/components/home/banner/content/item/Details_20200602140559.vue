<template>
  <div>
      <div v-for="(item,index) in itemArr" :key="index">
        <div class="title">{{item.name}}</div>
        <div class="title">{{item.tags}}</div>
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
</style>