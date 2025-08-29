<template>
  <div class="rating">
    <span v-for="n in 5" :key="n">
      {{ n <= roundedRate ? '★' : '☆' }}
    </span>
  </div>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
  rate: { type: Number, required: true },
});

// Redondeamos el valor al entero más cercano
const roundedRate = computed(() => Math.round(props.rate));
</script>

<style scoped>
.rating {
  font-size: 2rem;
  color: gold;
  margin-bottom: 1rem;
}
</style>
