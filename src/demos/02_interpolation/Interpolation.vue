<script setup>
// nom, role, montant, annee
const montant = 1500;
const annee = new Date().getFullYear();
const prime = 0.5;
const person = {
  fullname: 'Mouhamed',
  role: 'Dev',
};
</script>


<template>
  <section class="card">
    <h2>02_Interpolation</h2>
    <p>Dynamisation des vue avec du javascript</p>
    <ul>
      <li><strong>Nom:</strong>{{ nom }}</li>
      <li><strong>Role:</strong>{{ role }}</li>
      <li><strong>Montant:</strong>{{ montant.toLocaleString() }}</li>
      <li><strong>Annee:</strong>{{ annee }}</li>
      <li><strong>Salaire Net:</strong>{{montant + montant * prime}}</li>
    </ul>
  </section>
</template>


<style scoped>
ul {
  list-style: none;
}
</style>