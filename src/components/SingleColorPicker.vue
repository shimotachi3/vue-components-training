<template>
  <div class="single-color-picker">
    <label>{{ color.toUpperCase() }}:</label>
    <input 
      type="number" 
      :value="value" 
      min="0" 
      max="255" 
      @input="handleChange"
    />
    <div 
      class="color-preview" 
      :style="{ backgroundColor: bgColor }"
    ></div>
  </div>
</template>

<script setup>
const props = defineProps({
  color: { type: String, required: true },
  value: { type: Number, required: true },
});

const emit = defineEmits(["change"]);

const bgColor = computed(() => {
  return props.color === "r" 
    ? `rgb(${props.value},0,0)` 
    : props.color === "g" 
      ? `rgb(0,${props.value},0)` 
      : `rgb(0,0,${props.value})`;
});

function handleChange(event) {
  const newValue = Number(event.target.value);
  emit("change", newValue);
}
</script>

<style scoped>
.single-color-picker {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 0.5rem;
}

input {
  width: 60px;
  padding: 0.25rem;
}

.color-preview {
  width: 50px;
  height: 30px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
