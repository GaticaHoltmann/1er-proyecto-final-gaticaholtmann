<template>
    <div class="form-auth">
        <label for="user_email"> Email de usuario</label>
        <input type="email" name="" id="user_email">
        <label for="password">Contraseña</label>
        <input type="password" name="" id="password">
        <button class="btn btn-primary">Ingresar</button>
        <a href="#" @click="clickRegistry">Crear cuenta</a>

        <p>PF-GaticaHoltmann</p>
    </div>
</template>
<script>
    export default{
        methods:{
            clickRegistry(){
                this.$emit('registry')
            }
        }
    }
</script>
<style scoped>
    .form-auth{
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
    }
    .form-auth label,input,button,a {
        margin: 0.2rem;
    }
</style>