<template>
  <div class="carousel">
    <button @click="prevImage">Left</button>
    <img :src="images[currentIndex]" alt="carousel" class="carousel-img" />
    <button @click="nextImage">Right</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  images: { type: Array, required: true },
});

const currentIndex = ref(0);

function prevImage() {
  currentIndex.value =
    (currentIndex.value - 1 + props.images.length) % props.images.length;
}

function nextImage() {
  currentIndex.value = (currentIndex.value + 1) % props.images.length;
}
</script>

<style scoped>
.carousel {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.carousel-img {
  width: 200px;
  height: 200px;
  object-fit: cover;
  border-radius: 8px;
}
button {
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
}
</style>
