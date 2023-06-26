<template>
    <main>
        <AppMoviesList :moviesList="moviesList" :class="moviesList.length === 0 ? 'd-none' : 'd-block'"/>
        <AppSeriesList :seriesList="seriesList" :class="moviesList.length === 0 ? 'd-none' : 'd-block'"/>
    </main>
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

<style lang="scss">
    main{
        background-color: #1b1b1b;
    }
</style>