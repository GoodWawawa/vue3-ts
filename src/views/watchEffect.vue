<template>
  <button @click="handleClickCheck">点击</button>
</template>

<script setup lang="ts">
  import { ref, reactive, watchEffect } from 'vue'

  const count = ref(1)

  const list = reactive({})

  const handleClickCheck = () => {
    count.value++
  }

  const watch = watchEffect((onInvalidate) => {
    console.log('count的数值是',count.value)
    onInvalidate(() => {
      console.log('我出来喽')
    })

  })  //watchEffect 在count发生改变是会执行

  // watch() //当你不需要监听时

  setTimeout(() => {
    count.value++
  }, 1000)// 此时打印出 1 我出来喽 再打印 2  这是watchEffect 的副作用
  watchEffect(() => {}, {
    flush: 'post'
  }) //相当于watchPostEffect()

  watchEffect(() => {}, {
    flush: 'sync'
  }) //相当于watchSyncEffect()
</script>