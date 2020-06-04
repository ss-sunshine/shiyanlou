<template>
  <div>
    <div class="container">
      <div class="box d-f">
        
        <bannerimg></bannerimg>
      </div>
    </div>
  </div>
</template>

<script>
import Bannerimg from "./content/Bannerimg";
import Item from "./content/Item";
export default {
  name: "",
  props: {},
  components: {
    Bannerimg,
    Item
  },
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
.container{
  background: rgb(69, 103, 165);
  // height: 524px;
  .item{
    background: rgba(0, 0, 0, 0.1);
    z-index: 9;
  }
}
</style>