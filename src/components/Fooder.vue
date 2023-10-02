<template>
    <footer class="footer">
        <p>© {{date}}- Todos los derechos reservados app de citas de la realeza</p>
    </footer>
</template>
<script setup>
let date = new Date().getFullYear()

</script>

<style scoped>
.footer{
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100vw;
    height: 50px;
    background-color: #000;
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    font-family: 'Roboto', sans-serif;
    font-weight: 300;
    box-shadow: 0 0 10px rgba(0,0,0,0.5);
}
</style>