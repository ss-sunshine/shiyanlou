<template>
  <div>
      <div class="container banner">
          <div class="box">
              <item></item>
          <BannerImg></BannerImg>
          </div>
      </div>
  </div>
</template>

<script>
import BannerImg from './content/BannerImg'
import Item from './content/Item'
export default {
  name: "",
  props: {},
  components: {
      BannerImg,
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