<template>
    <article class="mb-3 col-2 me-1 p-0">
        <div class="flip">
            <div class="front" v-if="poster!==null">
                <img :src="`https://image.tmdb.org/t/p/w342/${poster}`" :alt="`${title}` + ' picture'">
            </div>
            <div class="front" v-else>
                <img src="../assets/no-poster.png" alt="Default Picture">
            </div>
            <div class="back p-2 overflow-y-scroll">
                <span>Title:</span>
                <h4> {{ title }}</h4>
                <span>Overview: </span>
                <p>{{overview}}</p>
                <span class="me-1">Language:</span>
                <img :src="`https://countryflagicons.com/FLAT/24/${language.toUpperCase()}.png`" :alt="`${language.toUpperCase()}`">
                <br>
                <span>Ranking: </span>
                <div v-if="convertedVote===5">
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                </div>
                <div v-else-if="convertedVote===4">
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                </div>
                <div v-else-if="convertedVote===3">
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                </div>
                <div v-else-if="convertedVote===2">
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                </div><div v-else-if="convertedVote===1">
                    <i class="fa-solid fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                </div>
                <div v-else>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                </div>
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