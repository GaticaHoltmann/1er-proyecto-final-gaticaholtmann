<template>
    <div class="header-store">
        <img src="../assets/site-logo.svg" alt="">
        <slot></slot>
    </div>
</template>
<script></script>
<style scoped>
    .header-store{
        display: flex;
        justify-content: space-between;
        background-color: blue;
        height: 15vh;
        grid-area: header;
        align-items: center;
    }

    .header-store img{
        height: 100%;
    }

</style>