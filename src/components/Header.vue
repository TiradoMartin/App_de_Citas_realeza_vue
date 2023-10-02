<template>
    <header id='header' class="header">
        <ul><i>Inicio<a href="#"></a></i>
        <i @click="modal">Acerca de</i>
        </ul>
      
    </header>
   


</template>
<style scoped>
.header{
    position: absolute;
    top: 0;
    left: 0;
 
 
}   
.header ul{
    display: flex;
    justify-content: space-around;
    list-style: none;
    background-color: #000;
    color: #fff;
    padding: 10px;
    margin: 0;
    width: 100vw;
    height: 50px;
    align-items: center;
    font-size: 20px;
    font-family: 'Roboto', sans-serif;
    font-weight: 300;
    box-shadow: 0 0 10px rgba(0,0,0,0.5);
    
}
.header ul i{
    cursor: pointer;
    align-items:center ;
   
}
</style>
<script setup>
import {ref,inject} from 'vue'
let visible=inject('visible')
const modal= ()=>{
    visible.value=!visible.value
}
 

</script>
```