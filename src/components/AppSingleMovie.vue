<template>
    <div>
        <article class="card mb-5 col-2 me-3 p-0">
                <div class="card-body text-center">
            <h5 class="card-title fw-bold">
                {{ title }}
            </h5>
            <p class="card-text">
            {{ otitle }}
            </p>    
            <p class="card-text">
                <img :src="`https://countryflagicons.com/FLAT/24/${language.toUpperCase()}.png`" alt="Flag">
            </p>
            <p class="card-text">
                {{ vote }}
            </p>
        </div>
    </article>
    </div>
</template>

<script>


export default {
    name: 'AppSingleMovie',
    data(){
        return{
            
        }
    },
    props:{
        title: String,
        otitle: String,
        language: String,
        vote: Number,
    },
    methods:{
        getflagImage(language) {
            const commonUrl = 'https://www.countryflagicons.com/FLAT/24/';
            const imgExt = '.png';
            return commonUrl + language.toUpperCase() + imgExt;
        },
    },
};
</script>

<style lang="">
    
</style>