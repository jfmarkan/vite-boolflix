<template>
    <div>
        <AppSingleSerie v-for="serie in seriesList"
            :title="serie.name"
            :otitle="serie.original_name"
            :language="serie.original_language"
            :vote="serie.vote_average"
        />
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

<style lang="">
    
</style>