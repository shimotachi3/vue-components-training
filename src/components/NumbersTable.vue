<template>
  <div class="numbers-table">
    <span
      v-for="n in limit"
      :key="n"
      :style="{ 
        display: 'inline-block', 
        width: '50px', 
        height: '50px', 
        lineHeight: '50px', 
        textAlign: 'center', 
        margin: '2px', 
        backgroundColor: n % 2 === 0 ? 'red' : 'white', 
        color: n % 2 === 0 ? 'white' : 'black', 
        border: '1px solid #ccc',
        borderRadius: '4px'
      }"
    >
      {{ n }}
    </span>
  </div>
</template>

<script setup>
const props = defineProps({
  limit: { type: Number, required: true },
});
</script>
