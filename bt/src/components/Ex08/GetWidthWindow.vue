<template>
  <div>
    <h3>Bài 8:</h3>
    <p>Chiều rộng của cửa sổ: {{ windowWidth }} px</p>
    <br />*****************************************
  </div>
</template>
  
  <script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const windowWidth = ref(window.innerWidth); 

// Hàm cập nhật chiều rộng khi cửa sổ được resize
const updateWindowWidth = () => {
  windowWidth.value = window.innerWidth;
};

// Lifecycle hook để đăng ký sự kiện resize
onMounted(() => {
  window.addEventListener("resize", updateWindowWidth);
});

// Lifecycle hook để gỡ bỏ sự kiện khi component bị loại bỏ
onBeforeUnmount(() => {
  window.removeEventListener("resize", updateWindowWidth);
});
</script>
  
  <style  >
</style>
  