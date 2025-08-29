<template>
  <div class="random-box">
    <p>Random value between {{ min }} and {{ max }} =&gt; {{ randomNumber }}</p>
  </div>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
  min: { type: Number, required: true },
  max: { type: Number, required: true },
});

// Calcula un número aleatorio en el rango [min, max]
const randomNumber = computed(() => {
  return Math.floor(Math.random() * (props.max - props.min + 1)) + props.min;
});
</script>

<style scoped>
.random-box {
  border: 1px solid #ccc;
  padding: 0.75rem 1rem;
  border-radius: 8px;
  max-width: 350px;
  margin-bottom: 1rem;
}
</style>
