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
  }) //copy可以修改
  const paste = readonly(copy)  //paste不可以修改
  
  const change = () => {
    copy.count++
    paste.count++ 
    paste.man.age = 22 //readonly 所有的都不能修改
    console.log(copy)
  console.log(paste)
  }

  const shallowPaste = shallowReadonly(copy)  // 浅只读 第一层不能修改 其他的都能修改
  const shallowChange = () => {
    shallowPaste.count++
    shallowPaste.man.age = 22 //shallowReadOnly 只有第一层不能修改 其他的可以修改
  }

  watchEffect (() => {
    console.log(copy.count)
  })
</script>