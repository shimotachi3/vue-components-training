<template>
  <img
    :src="currentImg"
    @click="toggleImage"
    alt="clickable"
    style="cursor: pointer; width: 200px; border-radius: 8px;"
  />
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  img: { type: String, required: true },
  imgClicked: { type: String, required: true },
});

const isClicked = ref(false);

const currentImg = ref(props.img);

function toggleImage() {
  isClicked.value = !isClicked.value;
  currentImg.value = isClicked.value ? props.imgClicked : props.img;
}
</script>
