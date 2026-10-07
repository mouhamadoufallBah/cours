<script setup>
const message = "test variable ";
</script>

<template>
  <section class="card">
    <h2>01_Hello_World</h2>
    <p>Premiere composant vue(sfc(Single File Component))</p>
    <div class="box"><strong>Message:</strong>{{ message.toUpperCase() }}</div>
  </section>
</template>

<style scoped>
.box {
  margin-top: 20px;
  padding: 12px;
  border: 1px dashed #ccc;
  border-radius: 10px;

}
</style>