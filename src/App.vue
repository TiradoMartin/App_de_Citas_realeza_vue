<template>
  <Header/>
  <div class="container">
    <Card v-show="visible"/>
    <div class="card">
      <div v-show="!visible" class="body-about">
        <h2>Esta es una aplicación creada por Martin Tirado para practicar los conceptos de Vue 3</h2>
        <h3>La misma cuenta con tres componentes que creada como una forma divertida de practicar lo aprendido de Vue 3</h3>
        <h4>Esta aplicación esta creada con Vue 3 y Vite 4</h4>
      
      </div>
    </div>
  </div>
 
  <Fooder/>
</template>

<script setup>
import { ref,provide } from 'vue'
import Header from './components/Header.vue'
import Fooder from './components/Fooder.vue'
import Card from './components/Card.vue'
const visible=ref(true)
provide('visible',visible)
</script>
<style scoped>
.container{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
}
.body-about{
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  height: 40vh;
  width: 68em;
  border: 1px solid #000;
  box-shadow: 0 0 10px rgba(0,0,0,0.5);
}
</style>