<template>
 <div>
     <div class="container">
         <div class="box">
         <div v-for="(item) in itemArr" :key="item.id">
         <div>{{item.name}}</div>
     </div>
     </div>
     </div>
 </div>
</template>

<script>
import axios from "axios";
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {
         itemArr:[]
     }
   },
   methods: {
       getData(){
           axios.get('http://120.78.14.107/api/v2/index/categories').then(res=>{
               console.log(res.data);
               this.itemArr=res.data
           }).catch(err=>{
               console.log(err);
           })
       }
   },
   mounted() {
       this.getData()
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>

</style>