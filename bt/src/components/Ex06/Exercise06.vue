<template>
  <div>
    <h3>Bài 6:</h3>
    <p>count : {{ count }}</p>
    <button @click="handleIncrement">Increment</button>
    <br>********************************
  </div>
</template>

<script setup>
import { onUpdated, ref } from 'vue';

    const count = ref(0)
    const handleIncrement =()=>{
        count.value++;
    }

    onUpdated(()=>{
    document.title = count.value; 

    })
</script>

<style>

</style>