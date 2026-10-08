<script setup>
import { computed, reactive } from "vue";

const cart = reactive([
  {
    nom: "Cahier",
    prix: 200,
    qte: 50,
  },
  {
    nom: "Stylo",
    prix: 100,
    qte: 70,
  },
  {
    nom: "Livre",
    prix: 2000,
    qte: 10,
  },
]);

const total = computed(() => {
  return cart.reduce((somme, currentValue) => {
    somme += currentValue.prix * currentValue.qte;
    return somme;
  }, 0);
});
</script>

<template>
  <section class="card">
    <h2>11 - computed()</h2>

    <ul>
      <li v-for="item in cart" :key="item.nom">
        {{ item.nom }}: {{ item.qte }} × {{ item.prix }} ->
        {{ item.qte * item.prix }} FCFA
      </li>
    </ul>

    <h3>Total : {{ total }} FCFA</h3>

    <p class="note">Le total se met à jour automatiquement.</p>
  </section>
</template>

<style scoped>
.card {
  padding: 16px;
  border: 1px solid #eee;
  border-radius: 12px;
}
.note {
  margin-top: 8px;
  color: #555;
}
</style>