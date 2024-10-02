<template>
  <div>
    <h3>Bài 5:</h3>
    <Exercise05Children v-if="isShow"/>
    <button  @click="handleToggle">Toggle</button>
    <br>*****************************
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Exercise05Children from './Exercise05Children.vue';

const isShow = ref(true);
    const handleToggle =()=>{
        isShow.value = !isShow.value
    }
</script>

<style>

</style>