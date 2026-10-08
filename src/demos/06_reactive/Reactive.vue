<script setup>
import { reactive, ref } from "vue";

const info = reactive({
  nom: "Idy",
  tel: "771234567",
  solde: 12000,
});

const cpt = ref(0);
const montantAJouter = ref(0);

function addSolde(solde) {
  cpt.value += 1;
  if (cpt.value > 10) {
    alert("Vous avez atteint la limite");
  }
  info.solde += solde;
}
</script>

<template>
  <section class="card">
    <h2>09 - reactive()</h2>

    <div class="box">
      <p><strong>Nom :</strong> {{ info.nom }}</p>
      <p><strong>Téléphone :</strong> {{ info.tel }}</p>
      <p><strong>Solde :</strong> {{ info.solde }} FCFA</p>
    </div>

    <div class="actions">
      <button @click="addSolde(5000)">+5 000</button>
      <button @click="addSolde(10000)">+10 000</button>
      <input
        type="number"
        placeholder="Autre montant"
        v-model="montantAJouter"
        @keyup.enter="addSolde(montantAJouter)"
      />
    </div>

    <p class="note">
      <code>reactive()</code> est idéal pour les objets complexes.
    </p>
  </section>
</template>

<style scoped>
.card {
  padding: 16px;
  border: 1px solid #eee;
  border-radius: 12px;
}
.box {
  padding: 12px;
  background: #fafafa;
  border-radius: 10px;
}
.actions {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}
button {
  padding: 8px 10px;
  border: 1px solid #ddd;
  border-radius: 8px;
  cursor: pointer;
}
.note {
  margin-top: 8px;
  color: #555;
}
</style>