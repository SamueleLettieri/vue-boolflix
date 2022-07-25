<template>
  <header>
    <div class="d-flex  justify-content-between pt-3 px-4">
        <h2>BOOLFLIX</h2>
        <div><input class="ms_input mt-2" type="text" v-model="searchBar" @keyup.enter="$emit('searchMovie', searchBar)"  v-on:keyup.enter="$emit('searchTv', searchBar)"></div>
    </div>    
  </header>
</template>

<script>
export default {
        data: function() {
        return{
            searchBar: " ",
        }
    }
}
</script>

<style lang="scss" scoped>
header{
    position: fixed;
    top: 0;
    width: 100%;
    background-color: black;
}

h2{
    color: red;
}

.ms_input{
    outline: none;
    height: 25px;
}

</style>