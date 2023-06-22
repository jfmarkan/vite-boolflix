<template>
    <div class="">
        <AppMoviesList :searchResult="searchResult"/>
    </div>
</template>

<script>
import AppMoviesList from './AppMoviesList.vue';


export default {
    name: 'AppMain',
    components:{
        AppMoviesList,
        AppSeriesList
    },
    props:{
        searchResult:Array,
    }
}
</script>

<style lang="">
    
</style>