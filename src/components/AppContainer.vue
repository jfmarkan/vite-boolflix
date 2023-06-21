<template>
    <AppHeader @searched="searchMovies" />
    <AppMain :moviesList="moviesList"/>
</template>

<script>
import AppHeader from './AppHeader.vue';
import AppMain from './AppMain.vue';
import axios from 'axios';

export default {
    name: 'AppContainer',
    components:{
        AppHeader,
        AppMain
    },
    data(){
        return {
        moviesList:[],
        apiUrl: 'https://api.themoviedb.org/3/search/movie?api_key=2c045d83106f88e7c47425fc16ecf05d',
        }
    },
    methods: {
        searchMovies(needle = ''){
            axios.get(this.apiUrl, {
                    params: {
                        query: needle
                    }
                })
                .then( (response) => {
                    this.moviesList = response.data.results;
                    console.log(response);
                    console.log
                })
                .catch(function (error) {
                    console.log(error);
                })
        }
    },
    created(){
        this.searchMovies();
    },
}
</script>

<style lang="">

</style>