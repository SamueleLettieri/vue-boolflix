<template>
  <div>
    <ul>
        <li>Titolo: {{serie.name}}</li>
        <li>Titolo Originale: {{serie.original_name}}</li>
        <li>Lingua: {{serie.original_language}}</li>
        <li>Voto: {{serie.vote_average}}</li>
    </ul>
  </div>
</template>

<script>
export default {
props:[
    "serie"
]
}
</script>

<style>
  
</style> 