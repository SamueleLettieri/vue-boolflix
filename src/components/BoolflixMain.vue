<template>
  <main class="p-5 mt-5 d-flex ms_background-grey" >
    <MovieMain v-for="movie in movies" :key="movie.id"
    :movie="movie"/>

    <TvMain v-for="serie in tv" :key="serie.id"
    :serie="serie"/>
  </main>
</template>

<script>
import MovieMain from './MovieMain.vue'
import TvMain from './TvMain.vue'
export default {
  components: {
    MovieMain,
    TvMain,
  },
props:{
    movies: {
        require: true,
        type: Array,
    },

    tv: {
        require: true,
        type: Array,
    }
}
}
</script>

<style lang="scss" scoped>
.ms_background-grey{
  width: 10053px;
  max-width: 10053px;
  height: 100vh;
  background-color: #434343;
}
</style>