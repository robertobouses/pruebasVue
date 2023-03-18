<script setup>
const name = "vue dinámico";
const styleColor="color: blue";
var styleColor2="color:orange";
const styleColor3="color:yellow";
const arrayColorees = ["blue","pink", "peru"];
const arrayAnimales = ["gato", "perro", "zorro", "elefante", "lobo"];
const activo =false
var nombreVariable = "NOMBRE VARIABLE";
let nombreLET ="NOMBRE LET";

const arrayFrutas = ["manzana", "pera", "platano"]

const arrayProductos=[
  {name: "Detergente",
  price:"$1",
  description: "Un jabón de lavadora",
},
{name: "Macarrones",
  price:"$1,30",
  description: "Pasta italiana",
},

{name: "Hilo",
  price:"$3,20",
  description: "De coser",
},
];


const objetoFruta = {
  name: "manzana",
  price:"22",
  description: "una manzana",
  id: 1,

};
  
const arrayStock=[
  {name: "pan",
price: "333",
description: "un pan",
stock: 30,
},
{name: "galleta",
price: "555",
description: "una galleta",
stock: 500,
},

]


const handleClick = ()=>{
  console.log("me diste click")
}



</script> 


<template>
  <h1>hola {{ name.toUpperCase() }}</h1>
  <h2>{{arrayColorees}}</h2>
  <h2 :style="styleColor3">en color amarillo{{ arrayColorees }}</h2>
  <h2>presentando un grupo de animales: {{ arrayAnimales }}</h2>
  <h2 :style="styleColor">Soy azulado</h2>
  <h1>{{ nombreLET }}</h1>
  <h2 :style="styleColor2">naranja {{ nombreVariable }} naranja</h2>
  <h3>este texto debería ir en blueviolet</h3>
  <h2>{{ activo? "Estoy activo" : "EStoy inactivo" }}</h2>
<p v-if="activo">Estoy activado</p>
<p v-if="!activo">estoy inactivado</p>

<h2 v-if="activo">Estoy activo</h2>
<p v-else>Estoy inactivo</p>

<h2 v-if="activo===true">ESTOY ACTIVO</h2>
<p v-else-if="activo===false">ESTOY INACTIVO</p>
<p v-else>ESTOY INDECISO</p>

<h2 v-show="activo">EStoy activo!!!</h2>
<h2 v-show="!activo">Estoy inactivo!!!</h2>

{{ arrayFrutas }}

<h2 v-for="fruta in arrayFrutas">
  {{ fruta }}
</h2>


<h2 v-for="(fruta, index) in arrayFrutas"
  :key="index"
  >{{index}}-{{fruta}}</h2>
  {{ fruta }}
 

  {{ arrayProductos }}
  <li v-for="productos in arrayProductos" :key="arrayProductos.name">
  {{ productos.name }}- {{ productos.price }}{{ productos.description }}
</li>
-------------------separacion---------------------
<h1>
---------------------------------------- </h1>
<li
v-for="(value, propiedad, index) in objetoFruta" :key="value">
{{index}} - {{propiedad}} : {{ value }}

</li>
-------------------separacion---------------------
<h1>
---------------------------------------- </h1>


<li>
<template v-for="item in arrayStock" :key="item.name">
  <li v-if="item.stock>400">{{ item.name }}-{{ item.price }}</li>
</template>
</li>

-------------------separacion---------------------
<h1>
---------------------------------------- </h1>
<button v-on:click="handleClick">Actívame</button>
<button @click="handleClick">Activame</button>



</template>








<style>
h1{color:green }
h2{color: red}
h3{color:blueviolet}
</style>