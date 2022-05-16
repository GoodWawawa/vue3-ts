<template>
  <p>{{ student.name }}</p>
  <p>{{ student.age }}</p>
  <p>{{ student.sex }}</p>
  <div @click="changeName">改变名字</div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const student = reactive({
  name: '李华',
  age: 18,
  sex: '男'
})

const changeName = () => {
  student.name = '小花'
} 
</script>