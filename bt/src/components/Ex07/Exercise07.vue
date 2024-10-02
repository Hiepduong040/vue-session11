<template>
  <div>
    <h3>Bài 7:</h3>
    <input type="text" v-model="inputValue">
    <br>********************************
  </div>
</template>

<script setup>
import { onUpdated, ref } from 'vue';

    const inputValue = ref("");

    onUpdated(()=>{
        document.title = inputValue.value; 
    })
</script>

<style>

</style>