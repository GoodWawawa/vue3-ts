<template>

  <button @click="change">点击</button>
</template>

<script setup lang="ts">
  import { reactive, readonly, watchEffect, shallowReadonly } from 'vue'

  const copy = reactive({
    count: 1, 
    man: {
      age: 21,
      sex: '男'
    }
  })
  const paste = readonly(copy)
  
  const change = () => {
    copy.count++
    paste.count++ 
    paste.man.age = 22 //readonly 所有的都不能修改
    console.log(copy)
  console.log(paste)
  }
  
  const shallowPaste = shallowReadonly(copy)
  const shallowChange = () => {
    shallowPaste.count++
    shallowPaste.man.age = 22 //shallowReadOnly 只有第一层不能修改 其他的可以修改
  }

  watchEffect (() => {
    console.log(copy.count)
  })
</script>