<template>
  <div class="ms_box mx-2">
      <div class=""><img class="ms_img" :src="`http://image.tmdb.org/t/p/w342/${element.poster_path}`" alt=""></div>
    <ul class="ms_position">
        <li>Titolo: {{element.title}}</li>
        <li>Titolo Originale: {{element.original_title}}</li>
        <li>Lingua: {{element.original_language}} <lang-flag :iso="element.original_language" /></li>
        <li>Voto:  <i class="fa-star" v-for="n in 5" :key="n" :class=" voto(element) ? 'fa-solid' : 'fa-regular' "></i></li> 
    </ul>
  </div>
</template>

<script>
export default {
props:[
    "element"
],
data:function() {
    return{

    }
},

methods:{
    voto(element){
        Math.ceil(element.vote_average / 2) 

        /* {{  voto(element) }} */
    }
}



}
</script>

<style lang="scss" scoped>
.ms_box{
    width: 345px;
    height: 500px;
    background-color: black;

}

.ms_img{
    width: 345px;
    object-fit: cover;
    height: 500px;
}

.ms_position{
    position: relative;
    bottom: 335px;
    color: white;
}

li{
    list-style: none;
}
</style> 