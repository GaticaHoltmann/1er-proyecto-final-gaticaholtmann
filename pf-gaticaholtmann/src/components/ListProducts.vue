<template>
    <div class="list-products">
        <slot></slot>
    </div>
</template>
<script></script>
<style scoped>
    .list-products{
        display: flex;
        justify-content: space-evenly;
        flex-wrap: wrap;
    }
</style>