<template>
  <div class="facebook">
    <div 
      v-for="profile in profiles" 
      :key="profile.id" 
      class="profile-card"
    >
      <img :src="profile.img" :alt="profile.firstName" />
      <div class="profile-info">
        <p><strong>First Name:</strong> {{ profile.firstName }}</p>
        <p><strong>Last Name:</strong> {{ profile.lastName }}</p>
        <p><strong>Country:</strong> {{ profile.country }}</p>
        <p><strong>Type:</strong> {{ profile.isStudent ? 'Student' : 'Teacher' }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import profiles from "../data/berlin.json";
</script>

<style scoped>
.facebook {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.profile-card {
  display: flex;
  align-items: center;
  border: 1px solid #ccc;
  padding: 0.5rem;
  border-radius: 8px;
}

.profile-card img {
  width: 100px;
  height: 100px;
  object-fit: cover;
  border-radius: 8px;
  margin-right: 1rem;
}

.profile-info p {
  margin: 0.2rem 0;
}
</style>
