<template>
   <div>
      <input type=" text" placeholder="cerca film o serie" v-model="inpuText">
      <button @click="$emit('search',inpuText)">cerca</button>
    </div>
</template>

<script>
export default {
     nome:"MyHeader",

 data(){
    return{
      inpuText : ""  
    }
    
 }
}
</script>

<style>

</style>