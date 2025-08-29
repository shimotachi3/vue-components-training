<template>
  <div class="rgb-color-picker">
    <SingleColorPicker 
      color="r" 
      :value="rValue" 
      @change="updateColor('r', $event)" 
    />
    <SingleColorPicker 
      color="g" 
      :value="gValue" 
      @change="updateColor('g', $event)" 
    />
    <SingleColorPicker 
      color="b" 
      :value="bValue" 
      @change="updateColor('b', $event)" 
    />
    <div 
      class="color-preview-full" 
      :style="{ backgroundColor: fullColor }"
    >
      {{ fullColor }}
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import SingleColorPicker from "./SingleColorPicker.vue";

const rValue = ref(0);
const gValue = ref(0);
const bValue = ref(0);

function updateColor(color, value) {
  if (color === "r") rValue.value = value;
  else if (color === "g") gValue.value = value;
  else if (color === "b") bValue.value = value;
}

const fullColor = computed(() => `rgb(${rValue.value},${gValue.value},${bValue.value})`);
</script>

<style scoped>
.rgb-color-picker {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  max-width: 250px;
}

.color-preview-full {
  width: 100%;
  height: 50px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  color: #fff;
  border: 1px solid #ccc;
  margin-top: 0.5rem;
}
</style>
