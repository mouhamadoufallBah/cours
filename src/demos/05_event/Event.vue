<script setup>
import { ref } from "vue";

const value = ref(1);
const cpt = ref(0);

function increment() {
  cpt.value += 1;
}

function reset() {
  cpt.value = 0;
}
</script>

<template>
  <div>
    <button @click="increment">Increment</button>
    <button @click="reset">Reset</button>
  </div>
  <div>
    <input type="number" min="1" v-model.number="cpt" />
  </div>
  <h4>{{ cpt }}</h4>
</template>

<style scoped>

</style>