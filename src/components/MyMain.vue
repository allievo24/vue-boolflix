<template>
  <div>
    <ul>
      <li>Titolo- titolo originale- voto- lingua</li>
      <li v-for="(film, index) in listaFilm" :key="index">
        {{ film.title }}------------
        {{film.original_title}}
        <!--integro bandiere con un v-bind -->
        <img v-if="bandiere.includes(film.original_language)" :src=" '../assets/img/ '+film.original_language+'.jpg'" alt="poster film"/>
        {{ film.original_language }}----
        {{film.vote_average}}-----
        {{ film.overview }}
       
          
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
      bandiere: ['en','it']
    };
  },
  methods: {
    
      
    }
  
};
</script>

<style lang="scss">
li {
  margin: 2rem 0;
}
</style>