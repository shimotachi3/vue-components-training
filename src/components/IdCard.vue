<template>
  <div class="id-card">
    <img :src="picture" :alt="`${firstName} ${lastName}`" />
    <div>
      <p><strong>First name:</strong> {{ firstName }}</p>
      <p><strong>Last name:</strong> {{ lastName }}</p>
      <p><strong>Gender:</strong> {{ gender }}</p>
      <p><strong>Height:</strong> {{ height }}cm</p>
      <p><strong>Birth:</strong> {{ birth.toDateString() }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  lastName: { type: String, required: true },
  firstName: { type: String, required: true },
  gender: { type: String, required: true },
  height: { type: Number, required: true },
  birth: { type: Date, required: true },
  picture: { type: String, required: true },
});
</script>

<style scoped>
.id-card {
  display: flex;
  align-items: center;
  gap: 1rem;
  border: 1px solid #ccc;
  padding: 1rem;
  border-radius: 12px;
  max-width: 400px;
}
.id-card img {
  width: 100px;
  height: 100px;
  object-fit: cover;
  border-radius: 8px;
  border: 1px solid #aaa;
}
</style>
