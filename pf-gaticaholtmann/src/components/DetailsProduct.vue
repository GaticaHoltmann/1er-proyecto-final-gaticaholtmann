<template>
    <div>
        <div>
            <img :src="image"/>
        </div>
        <div>
            <p>{{ serie }}</p>
            <h1>{{ name }}</h1>
            <p>{{ price }}</p>
            <slot></slot>
            <p>{{ description }}</p>
        </div>
        <button class="btn btn-danger">cerrar X</button>
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
<style></style>