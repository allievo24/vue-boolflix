<template>
  <div id="app">
    <MyHeader @search="ricerca" />
    <MyMain :listaFilm="listaFilm" :listaSerie="listaSerie" />
  </div>
</template>

<script>
import MyHeader from "./components/MyHeader.vue";
import MyMain from "./components/MyMain.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    MyHeader,
    MyMain,
  },

  data() {
    return {
      apilink: "https://api.themoviedb.org/3",
      privateKey: "ed5299798d3d71d806d1feda5d373225",
      lingua: "it-IT",
      listaFilm: [],
      listaSerie: [],
    };
  },

  methods: {
    ricerca(cerca) {
      axios
        .get(
          this.apilink +
            "/search/movie?api_key=" +
            this.privateKey +
            "&language=" +
            this.lingua +
            "&query=" +
            cerca
        )
        .then((rest) => {
          this.listaFilm = rest.data.results;
        })

        .catch((error) => {
          console.log(error);
        });

      axios
        .get(
          this.apilink +
            "/search/tv?api_key=" +
            this.privateKey +
            "&language=" +
            this.lingua +
            "&query=" +
            cerca
        )
        .then((rest) => {
          this.listaSerie = rest.data.results;
        })

        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss">
</style>
