<template>
  学习ref
  <button @click="count++">{{ count }}</button>
  <p>
    <button @click="count1++">{{ count1 }}</button>
    <!-- 在js里面通过.value 获取值 在html里面直接用count -->
  </p>
</template>

<script setup lang="ts">
import { ref } from 'vue'

//ref和不写ref就是一个响应式一个不响应式
const count = ref(0)
const count1 = 0

//.value可以直接获取到count的值
console.log(count)
console.log(count.value)

const list = ref({
  name: '种花家',
  age: '5k+'
})   //ref内部自动将对象、数组转化为reactive的代理对象
console.log(list.value.name) //当用ref定义数组/对象时，通过此方式来获值
</script>