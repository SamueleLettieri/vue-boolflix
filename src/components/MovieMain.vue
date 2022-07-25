<template>
  <div class="ms_box mx-2">
      <div class=""><img class="ms_img" :src="`http://image.tmdb.org/t/p/w342/${movie.poster_path}`" alt=""></div>
    <ul class="ms_position">
        <li>Titolo: {{movie.title}}</li>
        <li :class="{'d-none': movie.title === movie.original_title}">Titolo Originale: {{movie.original_title}}</li>
        <li>Lingua: {{movie.original_language}} <lang-flag :iso="movie.original_language" /></li>
        <li>Voto:  <i class="fa-star" v-for="n in 5" :key="n" :class="n <= voto() ? 'fa-solid ms_star-yellow' : 'fa-regular' "></i></li> 
        <li class="ms_overflow">overview: {{movie.overview}}</li>
    </ul>
  </div>
</template>

<script>
export default {
props:[
    "movie"
],
data:function() {
    return{

    }
},

methods:{
    voto(){
        return Math.ceil(this.movie.vote_average / 2) 

        /* {{  voto(movie) }} */
    }
}



}
</script>

<style lang="scss" scoped>
.ms_box{
    width: 345px;
    height: 500px;
    background-color: black;
    position: relative;

}

.ms_box:hover{
    border: 1px solid white;

}

.ms_img{
    width: 345px;
    object-fit: cover;
    height: 500px;
}

.ms_box:hover .ms_img{
    display: none;
}

.ms_position{
    position: absolute;
    top: 145px;
    color: white;
    display: none;
}

.ms_box:hover .ms_position{
    display: block;
}

li{
    list-style: none;
}

.ms_star-yellow{
    color: yellow;
}

.ms_overflow{
    height: 170px;
    overflow: auto;
}

.ms_overflow::-webkit-scrollbar {
  width: 5px;
  background: rgb(163, 163, 163); 
  border-radius: 4px;  
}
</style> 