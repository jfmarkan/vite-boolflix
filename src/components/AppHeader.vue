<template>
    <header>
        <div class="container-fluid">
            <div class="row justify-content-between me-2">
                <div class="col logo p-3">
                    <img src="../assets/boolflix-logo.png" alt="">
                </div>
                <div class="col d-flex align-self-center justify-content-end">
                    <div class="align-self-center ">
                        <input type="text" class="form-control form-control-sm" placeholder="Movie or Series name" aria-label="Movie name" aria-describedby="basic-addon1"  v-model="anySearch">
                    </div>
                    <div class="align-self-center">
                        <button @click="$emit('searched', anySearch)" class="btn btn-danger btn-sm ms-2">Search</button>
                    </div>
                    <div class="usertype mx-3 my-0 align-self-center">
                        <span class="align-self-center">JUNIOR</span>
                    </div>
                    <div class="position-relative align-self-center me-4">
                        <i class="fa-solid fa-bell"></i>
                        <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">
                            1
                            <span class="visually-hidden">unread messages</span>
                        </span>
                    </div>
                    <div class="profile align-self-center">
                        <img src="../assets/avatar.png" alt="">
                        <i class="fa-solid fa-chevron-down ms-2"></i>
                    </div>
                </div>
                
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'AppHeader',
    data() {
        return {
            anySearch : ''
        }
    },
    methods: {

    },
}
</script>

<style lang="scss">
    header{
        background-color: #1b1b1b;

        
    }

    .profile{
        height: 100%;
        img{
            height: 25px;
        }
        i{
            font-size: .6rem;

        }
    }

    i{
        font-size: 1.2rem;
        color: #FFF;
    }

    .usertype{
        color: #FFF;
    }
</style>