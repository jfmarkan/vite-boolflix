<template>
    <div class="container-fluid" id="movies">
        <p class="fw-bold pt-3">SERIES</p>
        <div class="row d-flex flex-nowrap overflow-x-scroll">
            <AppSingleSerie v-for="serie in seriesList"
                :title="serie.name"
                :otitle="serie.original_name"
                :language="serie.original_language"
                :vote="serie.vote_average"
                :img="serie.backdrop_path"
                :poster="serie.poster_path"
                :overview="serie.overview"
            />
        </div>
        
    </div>
</template>

<script>
import AppSingleSerie from './AppSingleSerie.vue';

export default {
    name: "AppSeriesList",
    props:{
        seriesList:Array,
    },
    components: { 
        AppSingleSerie 
    },
}

</script>

<style lang="scss" scoped>
    p{
        color:#FFF;
    }
</style>