<template>

</template>

<script lang="ts" setup>
  import { toRefs, reactive } from 'vue'

  const hero = reactive({
    name: '凯特琳',
    title: '皮城女警'
  })

  const heroRef = toRefs(hero)
  hero.name = '凯特琳1'  
  heroRef.name.value = '凯特琳'//两种修改方式
  console.log(heroRef)
  console.log(heroRef.name.value)
</script>