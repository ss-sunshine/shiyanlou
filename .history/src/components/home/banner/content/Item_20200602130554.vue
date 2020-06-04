<template>
  <div>
    <div class="itemArr" v-for="(item) in itemArr" :key="item.id">
      <div class="Arr-item p-r">
          {{item.name}}
    </div>
      <div class="line p-a-b"></div>
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
      itemArr: []
    };
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/categories")
        .then(res => {
          console.log(res.data);
          this.itemArr = res.data;
        })
        .catch(err => {
          console.log(err);
        });
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
.itemArr{
    background: rgba(0, 0, 0, 0.1);
    width: 224px;
    .Arr-item{
    width: 224px;
    padding: 18px 18px;
    color: white;
    .line{
    width: 224px;
    height: 1px;
    background: rgb(188,188,188);
}
    &:hover{
        background: white;
        color: black;
    }
}

}

</style>