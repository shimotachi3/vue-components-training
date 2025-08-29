<template>
  <div class="box-color" :style="{ backgroundColor: rgbColor }">
    <p>{{ rgbColor }}</p>
  </div>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
  r: { type: Number, required: true },
  g: { type: Number, required: true },
  b: { type: Number, required: true },
});

const rgbColor = computed(() => {
  return `rgb(${props.r}, ${props.g}, ${props.b})`;
});
</script>

<style scoped>
.box-color {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100px;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin-bottom: 1rem;
  font-weight: bold;
}
</style>
