<template>
    <article class="mb-3 col-2 me-1 p-0">
        <div class="flip">
            <div class="front">
                <img :src="`https://image.tmdb.org/t/p/w342/${poster}`" :alt="`${title}` + ' picture'">
            </div>
            <div class="back p-2">
                <span>Title:</span>
                <h4> {{ title }}</h4>
                <span>Overview: </span>
                <p>{{overview}}</p>
                <span class="me-1">Language:</span>
                <img :src="`https://countryflagicons.com/FLAT/24/${language.toUpperCase()}.png`" :alt="`${language.toUpperCase()}`">
                <br>
                <span>Ranking: </span>
                <p>{{convertedVote}}</p>
            </div>
        </div>
    </article>
</template>

<script>


export default {
    name: 'AppSingleSerie',
    data(){
        return{
            convertedVote:0,
        }
    },
    props:{
        title: String,
        otitle: String,
        language: String,
        vote: Number,
        img: String,
        overview:String,
        poster:String,
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