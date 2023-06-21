<template>
    <div>
        <div class="container">
            <div class="row justify-content-center">
                <div class="input-group mt-3 mb-4 w-75 ">
                    <span class="input-group-text" id="basic-addon1">Search a movie</span>
                    <input type="text" class="form-control" placeholder="Movie Name" aria-label="Movie name" aria-describedby="basic-addon1"  v-model="movieSearch"
                    @keyup.enter="$emit('searched', movieSearch)">
                </div>
            </div>
        </div>
    </div>
</template>

<script>


export default {
    name: 'AppHeader',
    data() {
        return {
            movieSearch : ''
        }
    },
    methods: {

    },
}

</script>

<style lang="">
    
</style>