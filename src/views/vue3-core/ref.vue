<template>
  学习ref
  <button @click="count++">{{ count }}</button>
  <p>
    <button @click="count1++">{{ count1 }}</button>
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

</script>