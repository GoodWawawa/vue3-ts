<template>
  <p>姓名：{{ list.name }}</p>
  <p>称号：{{ list.title }}</p>
  <button @click="change">换一个</button>
</template>

<script lang="ts" setup>
  import { reactive, toRef } from 'vue'

  const list = reactive({
    name: '蒙多医生',
    title: ''
  })

  const fooRef = toRef(list, 'title')
  fooRef.value = '祖安狂人'
  console.log(fooRef)

  const change = () => {
    list.name = '薇恩'
    //list.title = '暗夜猎手1' 
    // console.log(fooRef)  可以通过reactive 来修改fooRef的值
    fooRef.value = '暗夜猎手' // 也可以这样  二者更新互不影响
    console.log(fooRef)
  }
</script>