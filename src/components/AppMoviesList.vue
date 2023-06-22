<template>
    <div class="container-fluid" id="movies">
        <p class="fw-bold pt-3">MOVIES</p>
        <div class="row d-flex flex-nowrap overflow-x-scroll">
            <AppSingleMovie v-for="movie in moviesList"
            :title="movie.title"
            :otitle="movie.original_title"
            :language="movie.original_language"
            :vote="movie.vote_average"
            :img="movie.backdrop_path"
            :poster="movie.poster_path"
            :overview="movie.overview"
        />
        </div>
        
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

<style lang="scss" scoped>
    p{
        color:#FFF;
    }
</style>