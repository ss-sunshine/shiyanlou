<template>
  <div>
      <div class="container banner">
          <div class="box">
              <item></item>
          <bannerimg></bannerimg>
          </div>
      </div>
  </div>
</template>

<script>
import Bannerimg from './content/BannerImg'
import Item from './content/Item'
export default {
  name: "",
  props: {},
  components: {
      Bannerimg,
      Item
  },
  data() {
    return {
      
    };
  },
  methods: {
    
  },
  mounted() {
    this.getData();
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.banner{
    background: rgb(69,103,165);
}
</style>