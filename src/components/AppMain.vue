<template>
    <main>
        <AppMoviesList :moviesList="moviesList"/>
        <AppSeriesList :seriesList="seriesList" />
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