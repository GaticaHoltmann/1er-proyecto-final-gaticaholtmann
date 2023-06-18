<template>
    <div class="form-auth">
        <label for="name">Nombre</label>
        <input type="text" name="" id="name">
        <label for="lastname">Apellido</label>
        <input type="text" name="" id="lastname">
        <label for="user_email"> Email de usuario</label>
        <input type="email" name="" id="user_email">
        <label for="password">Contraseña</label>
        <input type="password" name="" id="password">
        <button class="btn btn-primary">Crear usuario</button>
    </div>
</template>
<script></script>
<style scoped>
.form-auth {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
}

.form-auth label,
input,
button,
a {
    margin: 0.2rem;
}</style>