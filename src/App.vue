<script setup>
import { computed, ref, reactive } from "vue";

// Person state
const person = reactive({
  name: "Robin Rana",
  age: 20,
});

// // Person state
// const person = ref({
//   name: "Robin Rana",
//   age: 20,
// });

// Increase person age
const ageIncrement = () => {
  person.age++;
};

// Decrement person age
const ageDecrement = () => {
  person.age--;
};

// Person computed logic
const isQualified = computed(() => {
  return person.age > 18 ? "Qualified" : "Not Qualified";
});

// Use method instead of computed
function isQualifiedFun() {
  return person.age > 18 ? "Qualified" : "Not Qualified";
}
</script>

<template>
  <h2>Name is {{ person.name }}</h2>
  <h2>Age is {{ person.age }}</h2>
  <h2>
    You are <span>{{ isQualifiedFun() }}</span>
  </h2>
  <button @click="ageIncrement">Increase Age</button>
  <button @click="ageDecrement">Decrement Age</button>
</template>
