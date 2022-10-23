<script setup>
import { ref, computed } from "vue";

const name = "Vue dinámico";
const counter = ref(0);
const increment = () => {
  counter.value++;
};

const decrement = () => {
  counter.value--;
};

const reset = () => {
  counter.value = 0;
};

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "nule";
  }
  if (counter.value > 0) {
    return "positive";
  }
  if (counter.value < 0) {
    return "negative";
  }
});

const arrayNumeros = ref([]);
const add = () => {
  arrayNumeros.push(arrayNumeros.value);
};
</script>

<template>
  <h1>Hola {{ name.toLocaleUpperCase() }}!</h1>
  <h2 :class="classCounter">{{ counter }}</h2>
  <button @click="increment">Aumentar</button>
  <button @click="reset">Resetear</button>
  <button @click="decrement">Disminuir</button>
  <button @click="add" :disabled="false">Add</button>
</template>

<style>
h1 {
  color: aqua;
}
.positive {
  color: green;
}

.negative {
  color: red;
}

.nule {
  color: blue;
}
</style>
