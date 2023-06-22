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
                <img :src="`https://image.tmdb.org/t/p/w342/${img}`" :alt="`${title}` + ' picture'">
            </p> 
            <p class="card-text">
                <img :src="`https://countryflagicons.com/FLAT/24/${language.toUpperCase()}.png`" :alt="`${language.toUpperCase()}`">
            </p>
            <p class="card-text">
                {{convertedVote}}
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
            convertedVote: 0,
        }
    },
    props:{
        title: String,
        otitle: String,
        language: String,
        vote: Number,
        img: String,
    },
    methods:{
        convertVote(number){
            return Math.ceil(number/2);
        }
    },
    mounted() {
        this.convertedVote = this.convertVote(this.vote)
    }
};
</script>

<style lang="">
    
</style>