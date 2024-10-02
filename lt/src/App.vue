<template>
  <div>
    <h1>lifecycle!</h1>
    <!-- 
      React :
        1. Khởi tạo create : khởi tạo state, props
        2. mount : gắn kết đưa vào DOM
        3. update : quá trình cập nhật thay đổi state (re-render)
        4. unmount : loại bỏ khỏi DOM
        Vuejs cũng tương tự gồm 4 giai đoạn
        khởi tạo- gắn kết- cập nhật - loại bỏ. 
      -->
    <Lifecycle v-if="isShow"  />
    <button @click="unmountComponent">click-unmount</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Lifecycle from "./components/Lifecycle.vue";
const isShow = ref(true);

const unmountComponent = () => {
  isShow.value=!isShow.value
};
</script>

<style>
</style>