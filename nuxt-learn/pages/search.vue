<template>
  <div class="page">888899898
    <ul><li v-for="(item,idx) in $store.state.navbar.app" :key="idx">{{item}}</li></ul>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  layout: 'search',
  data(){
    return{
      list:[]
    }
  },
  // async mounted() {
  //   let self = this;
  //   let {status,data:{list}} = await axios.get('/city/list')
  //   if(status === 200){
  //     self.list = list
  //   }
  // },
   async asyncData() {
    let {status,data:{list}} = await axios.get('http://127.0.0.1:3000/city/list')
    if(status === 200){
      return {
        list
      }
    }
  },
}
</script>
<style lang="css">
</style>
