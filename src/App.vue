<template>
  <div id="app">
   <MyHeader @search="searching"/>
   <MyMain/>
   
  </div>
</template>

<script>
import MyHeader from './components/MyHeader';
import MyMain from './components/MyMain';
import axios from'axios';


export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  methods:{
    ricerca(cerca){


      
    }
  }






}
</script>

<style lang="scss">
@import '~@fortawsome/fontawsome-free/css/all.css'

</style>
