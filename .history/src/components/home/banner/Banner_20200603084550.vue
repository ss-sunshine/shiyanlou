<template>
  <div>
    <div class="container">
      <div class="box d-f">
        <item></item>
        <bannerimg class="bannerimg"></bannerimg>
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
  
}
</style>