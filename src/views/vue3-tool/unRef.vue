<template>
  <button @click="useFoo">click me please</button>
</template>

<script lang="ts" setup>
  import { ref, unref } from 'vue';

  const cou = ref(1)
  const useFoo = ( data: any ) => {
    const unwrapped = unref(data)
    const c = unref(cou)
    console.log(unwrapped) //不是ref
    console.log(c) //是ref 打印出1 cou的内部值
  }
</script>