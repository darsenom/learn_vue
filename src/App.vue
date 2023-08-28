<script setup>
import { ref } from 'vue';
const counter = ref(0);
const increas = () => {
    counter.value++;
}

const decreas = () => {
    counter.value--;
}
</script>

<template>
    <div class="test">
        {{ counter }}
        <button @click="increas">Увеличить</button>
        <button @click="decreas">Уменьшить</button>
    </div>
</template>

<style scoped></style>
