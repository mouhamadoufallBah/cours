<script setup>
import { ref } from "vue";

const value = ref(1);
</script>

<template>
  <div>
    <button @click="value++">Increment</button>
    <button @click="value = 0">Reset</button>
  </div>
  <div>
    <input type="number" min="1" v-model.number="value" />
  </div>
  <h4>{{ value }}</h4>
</template>

<style scoped>
</style>