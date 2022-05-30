<template>
  <p>hello</p>
  <toRefs />
</template>

<script lang="ts" setup>
  import { ref } from 'vue'
  import toRefs from './views/vue3-tool/toRefs.vue'

  const newName = ref('麦林炮手')
</script>