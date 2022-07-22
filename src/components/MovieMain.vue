<template>
  <div>
    <ul>
        <li><img :src="`http://image.tmdb.org/t/p/w342/${element.poster_path}`" alt=""></li>
        <li>Titolo: {{element.title}}</li>
        <li>Titolo Originale: {{element.original_title}}</li>
        <li>Lingua: {{element.original_language}} <lang-flag :iso="element.original_language" /></li>
        <li>Voto: {{element.vote_average}}</li>
    </ul>
  </div>
</template>

<script>
export default {
props:[
    "element"
]

}
</script>

<style>
  
</style> 