<template>
  <div>
    <h3>Bài 2:</h3>
    <p>count: {{ count }}</p>
    <button @click="handleClick">Counter</button>
    <br />****************************
  </div>
</template>

<script setup>
import { onMounted, onUpdated, ref } from "vue";

const count = ref(0);
const handleClick = () => {
  count.value++;
};
onUpdated(() => {
  alert("Dữ liệu đã thay đổi");
});
onMounted(() => {
  console.log("Component đã được mount.");
});
</script>

<style>
</style>