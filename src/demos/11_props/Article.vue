<script setup>
    defineProps({
        product: Object,
        qte: Number
    })
    // const p = { id: 1, name: 'stylo', price: 200}
</script>

<template>
  <article class="card">
    <h3 class="name">{{ product.name }}</h3>
    <p class="price">{{ product.price }} FCFA</p>
    <p class="meta">ID: {{ product.id }}</p>
    <p class="meta">Qte: {{ qte }}</p>
  </article>
</template>

<style scoped>
.card { padding: 14px; border: 1px solid #eee; border-radius: 12px; background: #fff; }
.name { margin: 0; font-size: 16px; }
.price { margin: 6px 0 0; font-weight: 700; }
.meta { margin: 6px 0 0; color: #666; font-size: 12px; }
</style>
