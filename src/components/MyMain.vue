<template>
   <div>
     <ul>
        <li> Titolo- titolo originale- voto- lingua</li>
        <li v-for="(film, index) in listaFilm" :key="index">
        {{film.title}} - {{film.originale_title}}-{{film.vote_average}}-{{film.originale_language}}
     </li>
     </ul>
   </div>
  
</template>

<script>
export default {
    nome:"MyMain",
    props:{
       listaFilm :Array 
    }
}
</script>

<style>

</style>