<template>
  <div>
    <section class="film">
      <h2>Lista Film</h2>
         
         <div class="flip-card" v-for="(film, index) in listaFilm" :key="index">
            <div class="flip-card-inner">
               <div class="flip-card-front" >
                <img :src="'https://image.tmdb.org/t/p/w200/'+ film.poster_path" alt=""/>
               </div>
               <div class="flip-card-back"></div>
                
               {{ film.title }}------------
               {{film.original_title}}
               <!--integro bandiere con un v-bind -->
               <img class="flag" v-if="bandiere.includes(film.original_language)" 
               :src=" require('../assets/img/' + film.original_language + '.jpg')" />
               {{ film.original_language }}----
               {{film.vote_average}}-----
               {{ film.overview }}
            </div>

         </div>
    </section>
    <section class="serie">
      <h2>Lista Serie</h2>
         <ul>
               <li>Titolo- titolo originale- voto- lingua</li>
               <li v-for="(film, index) in listaSerie" :key="index">
               {{ film.name }}------------
               {{film.original_name}}
                <img :src="'https://image.tmdb.org/t/p/w200/'+ film.poster_path" alt=""/>

               <!--integro bandiere con un v-bind -->
               <img class="flag" v-if="bandiere.includes(film.original_language)" 
               :src=" require('../assets/img/' + film.original_language + '.jpg')" />
               {{ film.original_language }}----
               {{film.vote_average}}-----
               {{ film.overview }}

               </li>
            </ul>
    </section>
    
  </div>
</template>

<script>
export default {
  nome: "MyMain",
  props: {
    listaFilm: Array,
    listaSerie: Array,

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
   .film{
      display: flex;
         
         .flip-card {
         background-color: transparent;
         width: 300px;
         height: 300px;
         perspective: 1000px;
         }

         .flip-card-inner {
         position: relative;
         width: 100%;
         height: 100%;
         text-align: center;
         transition: transform 0.6s;
         transform-style: preserve-3d;
         box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
         }

         .flip-card:hover .flip-card-inner {
         transform: rotateY(180deg);
         }

         .flip-card-front, .flip-card-back {
         position: absolute;
         width: 100%;
         height: 100%;
         -webkit-backface-visibility: hidden;
         backface-visibility: hidden;
         }

         .flip-card-front {
         background-color: #bbb;
         color: black;

         }

         .flip-card-back {
        // background-color: #2980b9;
         color: white;
         transform: rotateY(180deg);
         }
            
         }
         .flag{            
            width: 50px;
         }
   
   



</style>