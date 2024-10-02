<template>
    <div>
      <h3>Bài 9:</h3>
      <h4>Ứng dụng đếm số</h4>
      <p>Count: {{ count }}</p>
      <br>***************************************
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, onBeforeUnmount } from 'vue';
  
  const count = ref(0);  
  let intervalId;  
  
  // Hàm để tăng giá trị count
  const incrementCount = () => {
    count.value++;
  };
  
  // Lifecycle hook để bắt đầu đếm khi component được mount
  onMounted(() => {
    intervalId = setInterval(incrementCount, 1000); // Tăng count mỗi giây
  });
  
  // Lifecycle hook để dừng đếm khi component bị unmounted
  onBeforeUnmount(() => {
    clearInterval(intervalId); // Dừng interval
  });
  </script>
  
  <style  >
  </style>
  