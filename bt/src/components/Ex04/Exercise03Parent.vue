<template>
  <div>
    <h3>Bài 4:</h3>
    <Exercise03Children :age="age" />
    <button @click="handleIncrease">Increase age</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Exercise03Children from './Exercise03Children.vue';

const age = ref(0);  

const handleIncrease = () => {
  age.value++;  
};
</script>

<style>
</style>
