<script setup>
const photo =
  "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQBfsihCjIV5Ok98Nq7kuvkzQdj0amGaw4zHjtUfkyKgg&s=10";
const isTrue = true;
</script>

<template>
  <section class="card">
    <h2>03_VBind</h2>
    <img :src="photo" alt="" srcset="" />
    <button :disabled=isTrue>CLique</button>
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