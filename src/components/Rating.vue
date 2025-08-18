<script setup>
import { computed } from 'vue';


const props = defineProps({
    rate: Number
})

const fillStarts = computed(() => {
    return Math.round(props.rate)
})

const emptyStars = computed(() => {
    return Math.round(5 - props.rate)
})

</script>

<template>
    <div>
        <span class="filled" v-for="r in fillStarts">★</span>
        <span class="empty"  v-for="r in emptyStars">☆</span>
    </div>
</template>

<style scoped>
span {
    font-size: 1.2rem;
}

.filled {
    color: gold;
}

.empty {
    color: #ccc;
}
</style>