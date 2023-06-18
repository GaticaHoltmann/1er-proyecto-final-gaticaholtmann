<template>
     <div class="card">
        <img :src=image class="card-img-top" alt="..." />
        <div class="card-body">
            <h5 class="card-title">{{ serie }}</h5>
            <a href="" @click.prevent="clickProduct" ><h4 class="card-title">{{ name }}</h4></a>
            <h5> $ {{ price }}</h5>
            <slot></slot>
        </div>
     </div>
</template>
<script>
export default {
    name: "CardInfo",
    props: {
        id: Number,
        image: String,
        name: String,
        description: String,
        serie: String,
        price: Number
    },
    methods:{
        clickProduct(){
            this.$emit('getProduct')
        }
    }
}

</script>
<style>
    .card{
        width: 20rem;
        margin: 1rem;
    }
</style>