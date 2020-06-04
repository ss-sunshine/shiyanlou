<template>
 <div>
     <div class="container">
       <item1></item1>
     </div>
 </div>
</template>

<script>
import Item1 from '../content/item/Item1'
import axios from "axios";
 export default {
   name: '',
   props: {
     
   },
   components: {
     Item1
   },
   data () {
     return {

     }
   },
   methods: {
     getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/louplus")
        .then(res => {
          console.log(res.data);
          // this.bannerArr = res.data;
          // if (res.data.code === 200) {
          //   this.bannerArr = res.data;
          // }
        })
        .catch(err => {
          console.log(err);
        });
    }
   },
   mounted() {
     this.getData();
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>

</style>