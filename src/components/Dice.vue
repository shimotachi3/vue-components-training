<template>
  <img
    :src="diceImg"
    @click="rollDice"
    alt="dice"
    style="cursor: pointer; width: 150px;"
  />
</template>

<script setup>
import { ref } from "vue";

// Inicializamos con un número aleatorio entre 1 y 6
const currentNumber = ref(randomDice());
const diceImg = ref(getDiceImg(currentNumber.value));

// Función para obtener un número aleatorio entre 1 y 6
function randomDice() {
  return Math.floor(Math.random() * 6) + 1;
}

// Función para obtener la ruta de la imagen según el número
function getDiceImg(number) {
  return `/img/dice${number}.png`;
}

function rollDice() {
  diceImg.value = `/img/dice-empty.png`; // muestra dado vacío
  setTimeout(() => {
    currentNumber.value = randomDice();
    diceImg.value = getDiceImg(currentNumber.value);
  }, 1000);
}
</script>
