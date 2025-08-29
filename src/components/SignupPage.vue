<template>
  <div class="signup-page">
    <h2>Signup Form</h2>
    
    <form @submit.prevent>
      <!-- Email -->
      <div class="form-group">
        <label for="email">Email:</label>
        <input
          id="email"
          type="email"
          v-model="email"
          :class="emailClass"
          placeholder="Enter your email"
        />
      </div>

      <!-- Password -->
      <div class="form-group">
        <label for="password">Password:</label>
        <input
          id="password"
          type="password"
          v-model="password"
          :class="passwordClass"
          placeholder="Enter your password"
        />
      </div>

      <!-- Nationality -->
      <div class="form-group">
        <label for="nationality">Nationality:</label>
        <select id="nationality" v-model="nationality">
          <option value="en">English</option>
          <option value="de">German</option>
          <option value="fr">French</option>
        </select>
      </div>
    </form>

    <!-- Display Info -->
    <p>Hello, your email is {{ email }}</p>
    <p>{{ greetingMessage }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const email = ref("");
const password = ref("");
const nationality = ref("en");

// Validación simple de email
const emailClass = computed(() => {
  if (!email.value) return "";
  const valid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email.value);
  return valid ? "valid" : "invalid";
});

// Validación simple de contraseña (mínimo 6 caracteres y contiene número)
const passwordClass = computed(() => {
  if (!password.value) return "";
  const strong = password.value.length >= 6 && /\d/.test(password.value);
  return strong ? "valid" : "invalid";
});

// Mensaje de saludo según nacionalidad
const greetingMessage = computed(() => {
  switch (nationality.value) {
    case "de":
      return "Hallo";
    case "fr":
      return "Bonjour";
    default:
      return "Hello";
  }
});
</script>

<style scoped>
.signup-page {
  max-width: 400px;
  margin: 1rem auto;
  font-family: sans-serif;
}

.form-group {
  margin-bottom: 1rem;
  display: flex;
  flex-direction: column;
}

input, select {
  padding: 0.5rem;
  border-radius: 6px;
  border: 1px solid #ccc;
  font-size: 1rem;
}

input.valid {
  border-color: green;
  background-color: #e0ffe0;
}

input.invalid {
  border-color: red;
  background-color: #ffe0e0;
}
</style>
