// aqui va el js 
<script setup>
// el setup indica el tipo, si es por opciones o composicion 
// ademas usa programacion reactiva 

const name = 'USUARIO';

const color= "color: blue";
const colorParrafo= "color: orange";

const vueText= 'VUE';

const arrayColor= ["yellow","blue","red"];
</script>

<!-- aqui va el html  -->
<template>
  <!-- en html vanila, osea el html puro. No se podria hacer esto y tendriamos que hacer más pasos con el js  --> 
  <h1>Hola {{ name }}</h1>
  <h2>Agregar Variables a HTML con JS en VUE</h2>

  <p>El titulo fue impreso mediante la interpolacion de texto.</p>

  <p>Esta interpolacion no se puede usar en atributos, solo variables.</p>
  
  <p>Esto es VUE Dinamico.</p>

  <h2 v-bind:style="color">v-bind para agregar estilos y variables js</h2>
  <p>El color azul de este titulo fue agregado mediante v-bind, que es una manera de agregar una variable a un atributo.<br>
  Es como tener la interpolaricacion pero para atributos. 
  </p>
  <p :style="colorParrafo">Una manera de escribirlo a breviado es con: <br>
      :style="color" <br>   
      Que es lo mismo que escribir: <br>
      v-bind:style="color"
  </p>
  <h2>Agregar funciones de JS en html</h2>
  <h3>Me gusta mucho {{ vueText.toLowerCase() }}</h3>
  <p>Se agrega solo expresiones no todo un js</p>
</template>

<!-- estilos o css  -->
<style>
h1{
  color: red;
  font-size: 5rem;
}
h2{
  color: rgb(100, 100, 206);
  font-size: 3rem;
}
</style>
