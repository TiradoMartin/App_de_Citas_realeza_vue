<template>
   <div class="card">
    <div class="header"><h2>Cena {{ num }} con el rey <span class="nombre">{{ nombre.toUpperCase() }}</span> </h2>
    <h4 class="precio"> {{ precio }}</h4>
    <h4 v-if="finDeSemana" class="bg-red">Solo fin de semana</h4>
    <h4 v-else class="bg-green">De lunes a Domingo</h4>
    <div v-if="precio<100" class="ofert">
        Ahora un 10% a hora paga: RD {{ precio-(precio*0.10) }} $<img src="oferta.jpg" alt="Oferta"></div>
</div>
    <div class="body"><img :src='chageImg' alt="oferta"></div>
    <div class="fooder-card">
        <button @click="next">Siguiente({{ num }}/{{numElemnt}})</button>
    </div>
   </div>
</template>
<script setup>
import {productos} from '../datos/datos.js';
import {ref, computed} from 'vue';
let num = ref(1);
let indice = ref(0);
let numElemnt = productos.length;
let nombre = ref(productos[num.value-1].nombre);
let precio = ref(productos[num.value-1].precio);
let finDeSemana = ref(productos[num.value-1].finDeSemana);
let img = ref(`https://www.html6.es/img/rey_${ nombre.value }.png`)
let chageImg = computed(() => {
    return `https://www.html6.es/img/rey_${ nombre.value }.png`
})
let next = () => {
    if(num.value < numElemnt){
        num.value++;
        indice.value++;
        nombre.value = productos[indice.value].nombre;
        precio.value = productos[indice.value].precio;
        finDeSemana.value = productos[indice.value].finDeSemana;
        //img.value = `https://www.html6.es/img/rey_${ nombre.value }.png`;
    }
    else{
        num.value = 1;
        indice.value = 0;
        nombre.value = productos[indice.value].nombre;
        precio.value = productos[indice.value].precio;
        finDeSemana.value = productos[indice.value].finDeSemana;
        /*Se comento estas linea para hacer esta misma funcionalidad con propiedades computables img.value = `https://www.html6.es/img/rey_${ nombre.value }.png`;*/ 
    }
}
</script>
<style scoped>
.card{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border: 1px solid #000;
    box-shadow: 0 0 10px rgba(0,0,0,0.5);
    border-radius: 0.7rem;
   
   width: 25em;
   min-height: 10em;
}
.body img{
    height: 15rem;
    
}
.body{
    display: flex;
    justify-content: center;
    align-items: center;
    flex: 1;
}
.footer-card{
    display: flex;
    justify-content: center;
    align-items: center;
    flex: 1;
    margin-top: 5rem;
}
button{
    padding: 0.5rem;
    border: none;
    border-radius: 0.4rem;
    background-color: #000;
    color: #fff;
    font-size: 1.5rem;
    cursor: pointer;
    margin-top: 0.7rem;
    margin-bottom: 0.4rem;
}
.bg-red{
    display: inline-block;
    background-color: red;
    color:#fff;
    border-radius: 0.4rem;
    padding: 0.2rem;
}
.bg-green{
    display: inline-block;
    background-color: green;
    color: #fff;
    border-radius: 0.4rem;
    padding: 0.2rem;
}
.card .header{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
}
.card .header .precio{
    font-size: 20px;
    color: #000;
    
}
.card .header .precio:after{
    content: '$';
    color: #000;
}
.card .header .precio:before{
    content: 'Precio: RD ';
    color: #000;
}
.card .header .ofert{
    display: flex;
    justify-content: center;
    align-items: center;
    flex: 1;
   margin:0.5rem 0;
    
}
.card .header .ofert img{
   
    width: 4rem;
   
}
.nombre{
    color:green;
}
</style>