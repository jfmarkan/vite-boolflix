<template>
    <div class="">
        <AppMoviesList :moviesList="moviesList"/>
        <AppSeriesList :seriesList="seriesList" />
    </div>
</template>

<script>
import AppMoviesList from './AppMoviesList.vue';
import AppSeriesList from './AppSeriesList.vue';


export default {
    name: 'AppMain',
    components:{
        AppMoviesList,
        AppSeriesList,
    },
    props:{
        moviesList:Array,
        seriesList:Array
    }
}
</script>

<style lang="">
    
</style>