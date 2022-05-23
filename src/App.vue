<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
// import { useMouse } from './mouse.js'
import 'animate.css'
import animateTest from './components/animateTest.vue'
// import HelloWorld from './components/HelloWorld.vue'
// import PropsTest from './components/PropsTest.vue'

// const msg = ref('人帅多金180')

// // const { x,y } = useMouse()

// provide('key', msg)

// const day = () => {
//   msg.value = '人傻钱多'
// }


</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
  <PropsTest :msg="msg" :msg2="msg" @some-event="day" /> -->
  <!-- <div>{{ x }}, {{ y }}</div> -->
  <animateTest />
  <EventCheck />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
