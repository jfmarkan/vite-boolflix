<template>
    <AppHeader @searched="searchAny" />
    <AppMain :moviesList="moviesList" :seriesList="seriesList"/>
</template>

<script>
import AppHeader from './AppHeader.vue';
import AppMain from './AppMain.vue';
import axios from 'axios';

export default {
    name: 'AppContainer',
    components:{
        AppHeader,
        AppMain,
    },
    data(){
        return {
        searchResult:[],
        moviesList:[],
        seriesList:[],
        movieApiUrl: 'https://api.themoviedb.org/3/search/movie',
        serieApiUrl: 'https://api.themoviedb.org/3/search/tv',
        }
    },
    methods: {
        searchAny(search = ''){
            axios.get(this.movieApiUrl, {
                params: {
                    api_key: '2c045d83106f88e7c47425fc16ecf05d',
                    query: search,
                }
            })
            .then( (response) => {
                this.searchResult = response.data.results;
                console.log(response);
            })
            .catch(function (error) {
                console.log(error);
            })
            axios.get(this.serieApiUrl, {
                    params: {
                        api_key: '2c045d83106f88e7c47425fc16ecf05d',
                        query: search,
                    }
                })
                .then( (response) => {
                    this.searchResult = response.data.results;
                    console.log(response);
                })
                .catch(function (error) {
                    console.log(error);
                })
        },
    },
    created(){
        this.searchAny();
    },
}
</script>

<style lang="">

</style>