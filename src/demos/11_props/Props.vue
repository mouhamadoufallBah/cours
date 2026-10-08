<script setup>
import Article from "./Article.vue";

const products = [
  { id: 1, name: "Stylo", price: 500, qte: 12 },
  { id: 2, name: "Cahier", price: 1500, qte: 32 },
  { id: 3, name: "Classeur", price: 3500, qte: 2 },
];
</script>

<template>
  <section>
    <h2>15 - Props & Validators</h2>
    <p>Le parent envoie un objet <code>product</code> au composant enfant.</p>

    <div class="grid">
      <Article v-for="p in products" :key="p.id" :product="p" :qte="p.qte" />
      <!-- <article class="card" v-for="p in products" :key="p.id">
        <h3 class="name">{{ p.name }}</h3>
        <p class="price">{{ p.price.toLocaleString() }} FCFA</p>
        <p class="meta">ID: {{ p.id }}</p>
      </article> -->
    </div>
  </section>
</template>

<style scoped>
.grid {
  display: grid;
  gap: 12px;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  margin-top: 12px;
}
@media (max-width: 900px) {
  .grid {
    grid-template-columns: 1fr;
  }
}

.card {
  padding: 14px;
  border: 1px solid #eee;
  border-radius: 12px;
  background: #fff;
}
.name {
  margin: 0;
  font-size: 16px;
}
.price {
  margin: 6px 0 0;
  font-weight: 700;
}
.meta {
  margin: 6px 0 0;
  color: #666;
  font-size: 12px;
}
</style>