<template>
  <button @click="check">click me</button>
</template>

<script lang="ts" setup>
  import { isRef } from 'vue'

  let count: unknown
  const check = () => {
    if (isRef(count)) {
      console.log('没想到吧，我是ref')
    } else {
      console.log('我竟然不是ref')
    }
  }
</script>