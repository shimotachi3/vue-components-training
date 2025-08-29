<template>
  <button
    :style="{ backgroundColor: currentColor, color: 'white', padding: '0.5rem 1rem', border: 'none', borderRadius: '8px', fontSize: '1rem', cursor: 'pointer' }"
    @click="incrementLike"
  >
    {{ likes }} Likes
  </button>
</template>

<script setup>
import { ref } from "vue";

const likes = ref(0);
const colors = ['purple','blue','green','yellow','orange','red'];
const colorIndex = ref(0);

const currentColor = ref(colors[colorIndex.value]);

function incrementLike() {
  likes.value += 1;
  colorIndex.value = (colorIndex.value + 1) % colors.length;
  currentColor.value = colors[colorIndex.value];
}
</script>
