<template>
<a href="#/HelloWord">helloWord</a>
<a href="#/propsTest">propsTest</a>
<component :is="currentView" />
</template>

<script lang="ts" setup>
import { ref, computed } from 'vue'
import helloWord from './HelloWorld.vue'
import propsTest from './PropsTest.vue'

const routes = {
  '/HelloWord': helloWord,
  '/PropsTest': propsTest
}

const currentPath = ref(window.location.hash)
window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})
const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/HelloWord']
})
</script>