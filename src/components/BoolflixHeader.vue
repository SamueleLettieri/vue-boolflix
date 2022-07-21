<template>
  <header class="d-flex m-3">
    <input type="text" v-model="searchBar" @keyup.enter="$emit('search', searchBar)">
    <div class="ms_button ms-3" ><a href="" @click="$emit('search', searchBar)">cerca</a></div>
  </header>
</template>

<script>
export default {
        data: function() {
        return{
            searchBar: "",
        }
    }
}
</script>

<style lang="scss" scoped>
a{
    text-decoration: none;
    color: white;
}

.ms_button{
    padding: 10px;
    background-color: blue;
}
</style>