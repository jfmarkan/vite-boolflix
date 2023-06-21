<template>
    <div class="">
        <AppMoviesList :moviesList="moviesList"/>
    </div>
</template>

<script>
import AppMoviesList from './AppMoviesList.vue';

export default {
    name: 'AppMain',
    components:{
        AppMoviesList,
    },
    props:{
        moviesList:Array,
    }
}
</script>

<style lang="">
    
</style>