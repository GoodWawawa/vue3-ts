<script setup lang="ts">
import { ref } from 'vue'
import 'animate.css'

defineProps<{ msg: string }>()

const name = ref('hao')

let show = true

const animation = ref()

const toggleShow = () => {
  show = !show
  animation.value = show === false ? 'animate__animated animate__lightSpeedOutRight' : 'animate__animated animate__lightSpeedInRight'
}
</script>

<template>
  <h1 class="animate__animated animate__backInDown">{{ msg }}</h1>
  <h2>{{ name }}</h2>
  <button @click="name = '好'">点击</button>
  <transition>
    <h1 v-if="show" :class="animation" >我自带动画是这样吗</h1>
  </transition>
  <button @click="toggleShow">切换</button>
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
