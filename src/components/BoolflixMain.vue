<template>
  <main>
    <MovieMain v-for="element in movies" :key="element.id"
    :element="element"/>

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