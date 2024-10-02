<template>
  <div>
    <h3>Bài 3:</h3>
    <p>Age: {{ age }}</p>
    <p>Company: {{ company }}</p>
    <button @click="randomAge">Random</button>
    <br />************************************
  </div>
</template>
  
  <script setup>
import { onMounted, onUpdated, ref, watch } from "vue";

const age = ref(1);
const companies = ["Rikkei Academy", "Rikkei Education", "Rikkei Fukuoka"];
const company = ref(companies[0]);

const randomAge = () => {
  // Cập nhật giá trị age ngẫu nhiên từ 1 đến 10
  age.value = Math.floor(Math.random() * 10) + 1;
};

onUpdated(() => {
  company.value = companies[(age.value - 1) % 3];
  console.log("Dữ liệu đã thay đổi: ", age.value);
});
onMounted(() => {
  console.log("Component đã được mount.");
});
</script>
  
  <style>
</style>