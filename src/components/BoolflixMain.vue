<template>
  <main>
    <MovieMain v-for="(element, index) in movies" :key="index"
    :element="element"/>
  </main>
</template>

<script>
import MovieMain from './MovieMain.vue'
export default {
  components: {
    MovieMain,
  },

props:{
    movies: {
        require: true,
        type: Array,
    }
}

}
</script>

<style>

</style>