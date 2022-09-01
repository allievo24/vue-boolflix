<template>
   <div>
     <ul>
        <li> Titolo- titolo originale- voto- lingua</li>
        <li v-for="(film, index) in listaFilm" :key="index">
        {{film.title}}------{{film.original_title}}------{{film.vote_average}}-----{{film.original_language}}----{{film.overview}}
        <img src="../assets/img/bd-italiana.jpg" alt=""/>
     </li>
     </ul>
   </div>

</template>

<script>
export default {
    nome:"MyMain",
    props:{
       listaFilm :Array 
    },
    data(){
      return{
         ita: "../assets/img/bd-italiana.jpg",
         En: "../assets/img/united_kingdom.jpg"
      }
    }
}
</script>

<style lang="scss">
 li{
   margin:2rem 0;
 }

</style>