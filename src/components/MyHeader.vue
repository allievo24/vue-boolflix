<template>
  <div class="header">
    <div class="logo">
      <strong>BOOLFLIX</strong>
    </div>
    <div class="input">
      <input type=" text" placeholder="cerca film o serie" v-model="inpuText" />
      <button @click="$emit('search', inpuText)"><strong>CERCA</strong></button>
    </div>
  </div>
</template>

<script>
export default {
  nome: "MyHeader",

  data() {
    return {
      inpuText: "",
    };
  },
};
</script>

<style lang="scss">
.header {
  height: 80px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: black;
  padding: 0 1rem;
  button {
    background: red;
    height: 25px;
    border-radius: 5px;
  }

  .logo {
    color: red;
    font-size: 2rem;
  }
}
</style>