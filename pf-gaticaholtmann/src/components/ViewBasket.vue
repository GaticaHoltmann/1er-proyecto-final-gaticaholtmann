<template>
    <div>
        <table class="table">
            <thead>
                <tr>
                    <th>Nombre producto</th>
                    <th>Descripción</th>
                    <th>Cantidad</th>
                    <th>Precio</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in items" :key="item.id">
                    <td>{{ item.name }}</td>
                    <td>{{ item.description }}</td>
                    <td>{{item.qty}}</td>
                    <td>{{ item.price }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
export default {
    props: {
        items: Object
    }
}
</script>
<style></style>