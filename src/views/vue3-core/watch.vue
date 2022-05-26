<template>
  <button @click="add">点击增加</button>
</template>

<script lang="ts" setup>
import { ref, reactive, watch } from 'vue'
  const count = ref(0)

  const add = () => {
    count.value++
    state.count++
  }
  // 侦听ref
  watch(count, (count, prevCount) => {
    console.log(count)
    console.log(prevCount)
  })  // 和watchEffect不同的是 watch 是懒侦听 只有他所监听的东西发生改变时才会执行

  //侦听getter函数
  const state = reactive({ count: 0 })
  watch(
    () => state.count,
    (num, prevNum) => {
      console.log('num的值为', num)
      console.log('prevNum的值为', prevNum)
    } 
  )

  // 侦听一个响应式对象是，侦听器自动处于深层级模式
  watch(state, () => {
    console.log('莫西莫西')
  })
</script>