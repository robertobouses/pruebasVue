<script setup>
const name = "vue dinámico";
const styleColor="color: blue";
const styleColor3="color:yellow";
const arrayColorees = ["blue","pink", "peru"];
const arrayAnimales = ["gato", "perro", "zorro", "elefante", "lobo"];

var nombreVariable = "NOMBRE VARIABLE";
let nombreLET ="NOMBRE LET";

</script>


<template>
  <h1>hola {{ name.toUpperCase() }}</h1>
  <h2>{{arrayColorees}}</h2>
  <h2>:style="styleColor3">en color amarillo{{ arrayColorees }}</h2>
  <h2>presentando un grupo de animales: {{ arrayAnimales }}</h2>
  <h2 :style="styleColor">Soy azulado</h2>
  <h1>{{ nombreLET }}</h1>
  <h2>:style="styleColor2">{{ nombreVariable }}</h2>
  <h3>este texto debería ir en blueviolet</h3>
  <h3>:style="styleColor3">esto debería estar en amarillo</h3>
</template>

<style>
h1{color:green }
h2{color: red}
h3{color:blueviolet}
</style>