<template>
  <div>
    <ul>
      <li>Titolo- titolo originale- voto- lingua</li>
      <li v-for="(film, index) in listaFilm" :key="index">
        {{ film.title }}------{{ lingua}}------{{
          film.vote_average}}-----{{ film.original_language }}----{{ film.overview }}
       
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  nome: "MyMain",
  props: {
    listaFilm: Array,
  },
  data() {
    return {
      bandiere:[en,it]
    };
  },
  methods: {
    lingua() {
      if (this.film.original_language.includes(this.bandiera)) {
       
       this.film.original_language == "../assets/img/united_kingdom.jpg"
      
      } else{
        
        (this.film.original_language == "../assets/img/bd-italiana.jpg")

      }
    },
  },
};
</script>

<style lang="scss">
li {
  margin: 2rem 0;
}
</style>