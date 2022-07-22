<template>
  <div id="app">
    <BoolflixHeader @searchMovie="getMovies" @searchTv="getTv"/>
    <BoolflixMain :movies="movies" :tv="tv"/>
  </div>
</template>

<script>
import axios from "axios";
import BoolflixHeader from './components/BoolflixHeader.vue'
import BoolflixMain from './components/BoolflixMain.vue'
export default {
  name: 'App',
  components: {
    BoolflixHeader,
    BoolflixMain,
  },
  data: function() {
    return{
      movies: [],
      tv: [],
      apiMovies: "https://api.themoviedb.org/3/search/movie?api_key=af1845e6d80bbef990493b6b3f54ff75",
      apiTv: "https://api.themoviedb.org/3/search/tv?api_key=af1845e6d80bbef990493b6b3f54ff75"

    }
  },
  methods: {
    getMovies(ricerca) {
      axios.get(`${this.apiMovies}&query=${ricerca}`)
      .then((result) => {
        console.log(result.data.results)
        this.movies = result.data.results
      })
      .catch((error) => {
        console.warn(error)
      })
    },

    getTv(ricerca) {
      axios.get(`${this.apiTv}&query=${ricerca}`)
      .then((result) => {
        console.log(result.data.results)
        this.tv = result.data.results
      })
      .catch((error) => {
        console.warn(error)
      })
    }
  },
  created(){
    this.getMovies();
    this.getTv();
  }
}
</script>

<style lang="scss">
  @import "~bootstrap/scss/bootstrap.scss";
</style>