<template>
    <div class="container-buttons">
        <button class="btn btn-success" @click="$emit('addProductBasket', this.counter)">Añadir al carrito</button>
        <input type="number" name="" id="" class="counter" min="1" placeholder="0" v-model="counter">
    </div>
</template>
<script>
export default {
    data() {
        return {
            counter : 1
        }
    }
}
</script>
<style scoped>
.counter {
    height: 10vh;
    width: 3vw;
}

.container-buttons {
    display: flex;
    justify-content: flex-end;
}
</style>