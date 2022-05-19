<template>
  <p>{{ student.name }}</p>
  <p>{{ student.age }}</p>
  <p>{{ student.sex }}</p>
  <p>{{ props.msg }}</p>
  <p>{{ props.msg2 }}</p>
  <p>{{ a }}</p>
  <div @click="$emit('someEvent')">改变名字</div>
  <button @click="a = '就是我'">改变</button>
  <button @click="count += count">{{ count }}</button>
</template>

<script setup lang="ts">
import { ref,reactive, inject } from 'vue'

const count = ref(2)

const props = defineProps<{
  msg: string,
  msg2: String
}>()

const a = inject('key')

const student = reactive({
  name: '',
  age: 18,
  sex: '男'
})
</script>