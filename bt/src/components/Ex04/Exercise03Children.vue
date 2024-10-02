<template>
  <div>
    <p>Age: {{ age }}</p>
    <br>******************************
  </div>
</template>

<script setup>
import { onMounted, onUpdated } from "vue";

const props = defineProps(["age"]);

onUpdated(() => {
  alert(`Giá trị của biến age đã thay đối}`);
});

onMounted(() => {
  console.log("Component đã được mount.");
});
</script>

<style >
</style>
