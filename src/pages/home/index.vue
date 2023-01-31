<template>
  <div>
    <h1>这是首页</h1>
    {{ count }}<button @click="addCount">增加</button>
    <button @click="timesCount">减小</button>
    <ul>
      <li v-for="val in arr" :key="val">{{ val }}</li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive, onMounted, onUpdated } from 'vue'
const count = ref<number>(1)
const arr = reactive<number[]>([1, 2, 3])
onMounted(() => {
  console.log('onMounted')
})
onUpdated(() => {
  console.log('修改了')
})
console.log('修改了吗')
const addCount = () => count.value++
const timesCount = () => count.value--
</script>

<style scoped>
</style>
