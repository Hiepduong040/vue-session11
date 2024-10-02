<template>
  <div>
    <h1>
      component lifecycle
      <!-- <p>{{ sayHello() }}</p> -->
      <ul>
        <li>Count C {{ countC }}</li>
        <li>Count D {{ countD }}</li>
      </ul>
      <button @click="handleChange">change count</button>
      <p>Kết quả sau khi tính tổng</p>
      <p>hàm tính toán bình thường {{ caculatorC() }}</p>
      <p>hàm tính toán dùng compoted {{ caculatorD }}</p>
    </h1>
  </div>
</template>

<script setup>
// import { computed, onBeforeMount, onBeforeUpdate, onMounted, onUpdated, ref,computed } from "vue";
import {
  
  onBeforeMount,
  //render
  onMounted,
  onBeforeUpdate,
  //re-render
  onUpdated,
  ref,
  computed,
  onBeforeUnmount,
  onUnmounted,
  
} from "vue";
const props = defineProps(["count"]);
const countC = ref(0);
const countD = ref(0);

onBeforeMount(() => {
  console.log("hook on before mount được gọi");
  // nơi gọi API lấy data dữ liệu
});
const sayHello = () => {
  console.log("hello!");
};

onMounted(() => {
  console.log("hook on mount đc gọi");
});
/*
        giai đoạn update
        onbefore update
        onupdated
    */
/**
 * Giai đoạn unmounting: giai đoạn hủy tức là component đc loại bỏ, 
 * tháo gỡ khỏi DOM
 */
onBeforeUpdate(() => {
  console.log("hook onBeforeUpdate đc gọi");
});
onUpdated(() => {
  console.log("hook onUpdated đc gọi");
});
onBeforeUnmount(()=>{
    console.log("hook onBeforeUnmount được gọi!");
    
})
onUnmounted(()=>{
    console.log("hook onUnmounted được gọi");
    
})
const handleChange = () => {
  countC.value++;
};

const caculatorC = () => {
  return countC.value ** 2;
};

const caculatorD = computed(() => {
  return countD.value ** 2;
});
</script>

<style>
</style>