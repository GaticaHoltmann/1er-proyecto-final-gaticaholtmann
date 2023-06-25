<template>
    <button class="btn btn-primary btn-shopping"
    @click="$emit('showBasket')"><i class="fa fa-shopping-basket" aria-hidden="true"></i>
    </button>
</template>
<script></script>
<style scoped>
.btn-shopping {
    margin: 0.5rem;
    height: 5vh;
    background: transparent;
}
</style>