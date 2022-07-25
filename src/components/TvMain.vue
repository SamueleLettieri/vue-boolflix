<template>
  <div>
    <ul>
        <li><img :src="`http://image.tmdb.org/t/p/w342/${serie.poster_path}`" alt=""></li>
        <li>Titolo: {{serie.name}}</li>
        <li>Titolo Originale: {{serie.original_name}}</li>
        <li>Lingua: {{serie.original_language}} <lang-flag :iso="serie.original_language" /></li>
        <li>Voto: {{ Math.ceil(serie.vote_average / 2)  }}</li> 
    </ul>
  </div>
</template>

<script>
export default {
props:[
    "serie"
],

data:function(){
    return{

    }
},

methods:{

},

created(){
    
}

}
</script>

<style>
  
</style> 