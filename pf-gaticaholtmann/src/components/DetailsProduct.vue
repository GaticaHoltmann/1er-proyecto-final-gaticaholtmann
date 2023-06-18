<template>
    <div class="view-details">
        <div>
            <img :src="image"/>
        </div>
        <div>
            <p>{{ serie }}</p>
            <h1>{{ name }}</h1>
            <p>{{ price }}</p>
            <p>{{ description }}</p>
            <slot></slot>
            <button class="btn btn-danger" @click="$emit('closeProduct')">cerrar X</button>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        id: Number,
        image: String,
        name: String,
        description: String,
        serie: String,
        price: Number
    }
}
</script>
<style scoped>
.view-details {
    display: flex;
    align-items: center;
    height: 70vh;
}
.view-details div, img{
    height: 70vh;
}
</style>