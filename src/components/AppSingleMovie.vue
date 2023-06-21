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
                {{ language }}<img src="https://www.countryflagicons.com/FLAT/24/DE.png" alt="">
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
        title:String,
        otitle:String,
        language:String,
        vote:Number,
    },
}
</script>

<style lang="">
    
</style>