<template>
 
  <div class="container">
    <Card v-show="visible"/>
    <div class="card">
      <div v-show="!visible" class="body">
        <h2>Esta es una aplicación creada por Martin Tirado para practicar los conceptos de Vue 3</h2>
        <h3>La misma cuenta con tres componentes que creada como una forma divertida de practicar lo aprendido de Vue 3</h3>
        <h4>Esta aplicación esta creada con Vue 3 y Vite 4</h4>
      
      </div>
    </div>
  </div>
 
 
</template>

<script setup>
const visible=true
</script>
<style scoped>
.container{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
}
</style>