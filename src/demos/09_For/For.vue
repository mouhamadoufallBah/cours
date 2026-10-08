<script setup>
import { ref } from "vue";

const products = ref([
  {
    id: crypto.randomUUID(),
    nom: "Cahier",
    prix: 200,
    qte: 50,
  },
  {
    id: crypto.randomUUID(),
    nom: "Stylo",
    prix: 100,
    qte: 70,
  },
  {
    id: crypto.randomUUID(),
    nom: "Livre",
    prix: 2000,
    qte: 10,
  },
]);

function supprime(id) {
  products.value = products.value.filter((one) => one.id !== id);
}
</script>

<template>
  <section class="card">
    <h2>13 - Lists</h2>

    <ul>
      <li v-for="p in products" :key="p.id">
        {{p.nom}} - {{p.prix}} FCFA
        <button @click="supprime(p.id)">❌</button>
      </li>
    </ul>
  </section>
</template>

<style scoped>
.card {
  padding: 16px;
  border: 1px solid #eee;
  border-radius: 12px;
}
li {
  display: flex;
  justify-content: space-between;
  width: 250px;
}
button {
  border: none;
  background: none;
  cursor: pointer;
}
</style>