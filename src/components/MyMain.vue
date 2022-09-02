<template>
  <div>
    <section class="film">
      <h2>Lista Film</h2>

      <div class="flip-card" v-for="(film, index) in listaFilm" :key="index">
        <div class="flip-card-inner">
          <div class="flip-card-front">
            <img
              :src="'https://image.tmdb.org/t/p/w200/' + film.poster_path"
              alt=""
            />
          </div>
          <div class="flip-card-back">
            <h3>{{ film.title }}</h3>
            <h3>{{ film.original_title }}</h3>

            <!--integro bandiere con un v-bind -->
            <img
              class="flag"
              v-if="bandiere.includes(film.original_language)"
              :src="require('../assets/img/' + film.original_language + '.jpg')"
            />
            <h3>  {{ film.vote_average }}</h3>
          
            <div class="trama">
              {{ film.overview }}
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="serie">
      <h2>Lista Serie</h2>
      <div class="flip-card" v-for="(film, index) in listaSerie" :key="index">
        <div class="flip-card-inner">
          <div class="flip-card-front">
            <img
              :src="'https://image.tmdb.org/t/p/w200/' + film.poster_path"
              alt=""
            />
          </div>
          <div class="flip-card-back">
            <h3>{{ film.name }}</h3>
            <h3>{{ film.original_name }}</h3>

            <!--integro bandiere con un v-bind -->
            <img
              class="flag"
              v-if="bandiere.includes(film.original_language)"
              :src="require('../assets/img/' + film.original_language + '.jpg')"
            />
            {{ film.vote_average }}
            <div class="trama">
              {{ film.overview }}
            </div>
          </div>
        </div>
      </div>
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
      bandiere: ["en", "it"],
    };
  },
  methods: {},
};
</script>

<style lang="scss">
.film,
.serie {
   display:flex;
   flex-wrap: wrap;
   border: solid 2px black;
   h2{
     width: 100%;
   }
   

  .flip-card {
    background-color: transparent;
   //width: 250px;
   height: 300px;
    perspective: 1000px;
    margin-bottom: 2rem;
    overflow: auto;
    width: calc(100% /5);

  }

  .flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  }

  .flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
  }

  .flip-card-front,
  .flip-card-back {
    position: absolute;
    width: 100%;
    //height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;

    img {
      width: 100%;
    }
  }

  .flip-card-front {
    background-color: #bbb;
    color: black;
  }

  .flip-card-back {
    transform: rotateY(180deg);
    color: white;
    background: rgb(200, 20, 20);
    
  
    .flag {
       width: 10%;
     }
     .trama{
      padding: 1rem;
   
     }
  }
}


</style>