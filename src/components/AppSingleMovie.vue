<template>
    <article class="mb-3 col-2 me-1 p-0">
        <div class="flip">
            <div class="front">
                <img :src="`https://image.tmdb.org/t/p/w342/${poster}`" :alt="`${title}` + ' picture'">
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
                <p>{{convertedVote}}</p>
            </div>
        </div>
    </article>
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

<style lang="scss">
    .flip {
    position: relative;
    >.front,
    >.back {
        background-color: #C0C0C0;
        font-size: .75rem;
        display: block;
        transition-timing-function: cubic-bezier(.175, .885, .32, 1.275);
        transition-duration: .5s;
        transition-property: transform, opacity;
    }
    >.front {
        transform: rotateY(0deg);
        img{
            width: 100%;
            height: 375px;
            object-fit: fill;
        }
    }
    >.back {
        position: absolute;
        opacity: 0;
        top: 0px;
        left: 0px;
        width: 100%;
        height: 100%;
        transform: rotateY(-180deg);
    }
    &:hover {
        >.front {
            transform: rotateY(180deg);
        }
        >.back {
            opacity: 1;
            transform: rotateY(0deg);
        }
    }
    &.flip-vertical {
        >.back {
            transform: rotateX(-180deg);
        }
        &:hover {
            >.front {
                transform: rotateX(180deg);
            }
            >.back {
                transform: rotateX(0deg);
            }
        }
    }
    
}

</style>