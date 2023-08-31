<script setup>
const car = defineProps({
    car: {
        type: Object,
        required: true,
    },
})
</script>

<template>
    <div class="car">
      <img :src="this.car.image" alt="car" />
      <h2>{{ this.car.brand }}</h2>
      <p>Цена: {{ this.car.price }}</p>
      <p>Год выпуска: {{ this.car.year }}</p>
      <p>Объем двигателя: {{this.car.volume }}</p>
      <p>Цвет: {{ this.car.color }}</p>
    </div>
  </template>

<style scoped></style>