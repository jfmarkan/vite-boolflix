<template>
    <div>
        <AppSingleMovie v-for="result in searchResult"
            :title="result.title"
            :otitle="result.original_title"
            :language="result.original_language"
            :vote="result.vote_average"
            :img="result.backdrop_path"
        />
    </div>
</template>

<script>
import AppSingleMovie from './AppSingleMovie.vue';

export default {
    name: "AppMoviesList",
    props:{
        searchResult:Array,
    },
    components: { 
        AppSingleMovie 
    },
}

</script>

<style lang="">
    
</style>