<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const name = ref('hao')
</script>

<template>
  <h1>{{ msg }}</h1>
  <h2>{{ name }}</h2>
  <button @click="name = '好'">点击</button>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
