<script setup>
import { ref, computed } from 'vue'

const name = "Vue dinámico";

const counter = ref(0);

const increment = ()=> {
  counter.value++;
};

const decrement = ()=> {
  counter.value--;
};

const reset = ()=> {
  counter.value = 0;
};

const classCounter = computed(() => {
  if (counter.value === 0) {
    return 'zero';
  }
  if (counter.value > 0) {
    return 'positive';
  }
  if (counter.value < 0) {
    return 'negative';
  }
});
</script>

<template>
  <h2 :class="classCounter">{{ counter }}</h2>  
  <button @click="increment">AUMENTAR</button>
  <button @click="decrement">DECRECER</button>
  <button @click="reset">RESET</button>
</template>

<style>
.positive {
  color: green;
}
.negative {
  color: red;
}
.zero {
  color: peru;
}
</style>
