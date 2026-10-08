<script setup>
import { ref } from "vue";

const nom = ref("");
const telephone = ref("");
const contact = ref([]);

function add() {
    if(!nom.value.trim() || !telephone.value.trim) return;

  contact.value.unshift({
    id: Math.random(),
    nom: nom.value,
    telephone: telephone.value,
  });

  nom.value = "";
  telephone.value = "";

  console.log(contact.value);
}
</script>

<template>
  <section class="card">
    <div class="card">
      <h3>EventForm</h3>

      <form class="form" @submit.prevent="add">
        <input class="input" placeholder="Nom complet" v-model="nom" />
        <input class="input" placeholder="Téléphone" v-model="telephone" />
        <button type="submit">Enregistrer</button>
      </form>

      <p class="note">Démo : <code>...</code>, <code>...</code>.</p>
    </div>

    <ul>
      <li v-for="item in contact.value" :key="item.id">
        {{ item.nom }}
      </li>
    </ul>
  </section>
</template>

<style scoped>
.card {
  padding: 14px;
  border: 1px solid #eee;
  border-radius: 12px;
  margin-top: 12px;
}
.form {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}
.input {
  padding: 8px 10px;
  border: 1px solid #ddd;
  border-radius: 10px;
  min-width: 220px;
}
button {
  padding: 8px 10px;
  border-radius: 10px;
  border: 1px solid #ddd;
  background: white;
}
.empty {
  margin-top: 10px;
  color: #666;
}
.list {
  margin: 10px 0 0;
  padding-left: 18px;
}
.note {
  margin-top: 8px;
  color: #555;
}
</style>