<template>
    <div>
        <AppSingleMovie v-for="movie in moviesList"
            :title="movie.title"
            :otitle="movie.original_title"
            :language="movie.original_language"
            :vote="movie.vote_average"
            :img="movie.backdrop_path"
        />
    </div>
</template>

<script>
import AppSingleMovie from './AppSingleMovie.vue';

export default {
    name: "AppMoviesList",
    props:{
        moviesList:Array,
    },
    components: { 
        AppSingleMovie 
    },
}

</script>

<style lang="">
    
</style>