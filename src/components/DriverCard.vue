<template>
  <div class="driver-card">
    <img :src="img" :alt="name" class="driver-img" />
    <div class="driver-info">
      <h2>{{ name }}</h2>
      <Rating :rate="rating" />
      <p>{{ car.model }} - {{ car.licensePlate }}</p>
    </div>
  </div>
</template>

<script setup>
import Rating from "./Rating.vue";

const props = defineProps({
  name: { type: String, required: true },
  rating: { type: Number, required: true },
  img: { type: String, required: true },
  car: {
    type: Object,
    required: true,
    validator: (c) => c.model && c.licensePlate,
  },
});
</script>

<style scoped>
.driver-card {
  display: flex;
  align-items: center;
  background-color: #455eb5;
  color: white;
  border-radius: 12px;
  padding: 1rem;
  margin-bottom: 1rem;
  max-width: 500px;
  gap: 1rem;
}

.driver-img {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid white;
}

.driver-info h2 {
  margin: 0;
  font-size: 1.2rem;
}

.driver-info p {
  margin: 0.25rem 0 0 0;
}
</style>
