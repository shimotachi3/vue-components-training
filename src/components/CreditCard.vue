<template>
  <div class="credit-card" :style="{ backgroundColor: bgColor, color: color }">
    <div class="card-type">
      <img
        v-if="type === 'Visa'"
        src="https://upload.wikimedia.org/wikipedia/commons/4/41/Visa_Logo.png"
        alt="Visa"
      />
      <img
        v-else-if="type === 'Master Card'"
        src="https://upload.wikimedia.org/wikipedia/commons/0/04/Mastercard-logo.png"
        alt="Master Card"
      />
    </div>
    <div class="card-number">•••• •••• •••• {{ lastDigits }}</div>
    <div class="card-info">
      <span>Expires {{ formattedMonth }}/{{ expirationYear.toString().slice(-2) }}</span>
      <span class="bank">{{ bank }}</span>
    </div>
    <div class="card-owner">{{ owner }}</div>
  </div>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
  type: { type: String, required: true },
  number: { type: String, required: true },
  expirationMonth: { type: Number, required: true },
  expirationYear: { type: Number, required: true },
  bank: { type: String, required: true },
  owner: { type: String, required: true },
  bgColor: { type: String, required: true },
  color: { type: String, required: true },
});

const lastDigits = computed(() => props.number.slice(-4));
const formattedMonth = computed(() =>
  props.expirationMonth < 10 ? "0" + props.expirationMonth : props.expirationMonth
);
</script>

<style scoped>
.credit-card {
  width: 320px;
  height: 180px;
  border-radius: 12px;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  font-family: monospace;
  margin-bottom: 1rem;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
}

.card-type {
  display: flex;
  justify-content: flex-end;
}

.card-type img {
  width: 60px;
  height: auto;
}

.card-number {
  font-size: 1.2rem;
  letter-spacing: 2px;
  text-align: center;
}

.card-info {
  display: flex;
  justify-content: space-between;
  font-size: 0.9rem;
}

.card-owner {
  font-size: 0.9rem;
}
</style>
