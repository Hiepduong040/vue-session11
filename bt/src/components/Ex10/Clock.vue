<template>
  <div>
    <h3>Bài 10:</h3>
    <p>Đồng hồ hiện tại: {{ formattedTime }}</p>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount, computed } from 'vue';

const currentTime = ref(new Date()); 
let intervalId; // Biến để lưu ID của interval

// Hàm để cập nhật thời gian hiện tại
const updateTime = () => {
  currentTime.value = new Date();
};

// Computed property để định dạng thời gian
const formattedTime = computed(() => {
  const hours = String(currentTime.value.getHours()).padStart(2, '0');
  const minutes = String(currentTime.value.getMinutes()).padStart(2, '0');
  const seconds = String(currentTime.value.getSeconds()).padStart(2, '0');
  return `${hours} : ${minutes} : ${seconds}`;
});

// Lifecycle hook để bắt đầu cập nhật thời gian khi component được mount
onMounted(() => {
  updateTime(); // Cập nhật thời gian ngay khi component được mount
  intervalId = setInterval(updateTime, 1000); // Cập nhật thời gian mỗi giây
});

// Lifecycle hook để dọn dẹp bộ nhớ khi component bị unmounted
onBeforeUnmount(() => {
  clearInterval(intervalId); // Dừng interval
});
</script>

<style  >
</style>
