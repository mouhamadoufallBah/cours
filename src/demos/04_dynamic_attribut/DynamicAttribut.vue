<script setup>
import { ref } from "vue";

const status = ref("Warning");
</script>

<template>
  <section class="card">
    <h2>04_Dynamic_attribut</h2>
    <div class="row">
      <span >Statut: {{ status }}</span>
      <select v-model="status">
        <option value="Success">Success</option>
        <option value="Warning">Warning</option>
        <option value="Danger">Danger</option>
      </select>

      <p>{{ status }}</p>
    </div>
    <div
      class="bar"
      :style="{
        width:
          status === 'Danger' ? '20%' : status === 'Warning' ? '50%' : '80%',
      }"
    ></div>
  </section>
</template>

<style scoped>
.row {
  display: flex;
  gap: 12px;
  align-items: center;
}

.badge {
  padding: 6px 10px;
  border-radius: 999px;
  font-weight: bold;
  border: 1px solid #ddd;
}

.success {
  background-color: #e9f7ef;
}
.warning {
  background-color: #fff7ef;
}
.danger {
  background-color: #fdecea;
}

.bar {
  height: 10px;
  border-radius: 999px;
  border: 1px solid #eee;
  background: #ddd;
  margin-top: 14px;
}

select {
  padding: 8px 10px;
  border: 1px solid #ddd;
  border-radius: 10px;
}
</style>