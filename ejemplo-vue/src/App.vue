<script setup>
// aqui va el js 

// - - - trabajado como opciones; funciones- - -
// export default{
//   data(){
//     return {
//       saludo: 'Hola Mundo'
//     }
//   }
// }

// // - - - trabajando por objetos o components - - - 
// import {ref} from 'vue';
//   const saludo = ref('Hola Mundo!!!');
//   // usa programacion reactiva 
</script>

<template>
  <!-- aqui va el html  -->

  <!-- se agrega contenido mediante variables al html  -->
  <h1>{{ saludo }}</h1>
</template>

<!-- scoped para solo el componente pero sin el queda global los estilos  -->
<style scoped>
  /* aqui va el css  */

</style>
