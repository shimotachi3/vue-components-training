<script setup>
defineProps(['lastName', 'firstName'])
</script>

<template>
    <div>
        <p><strong>First Name:</strong> {{ firstName }}</p>
        <p><strong>Last Name:</strong> {{ lastName }}</p>

    </div>
</template>

<style scoped>
div {
    border: 1px solid black;
    padding: 1rem;
    max-width: 500px;
}
</style>