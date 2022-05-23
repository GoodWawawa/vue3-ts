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
  <button @click="open = true">点我打开模态框</button>

  <Teleport to="body">
    <div v-if="open" class="modal animate__animated animate__jackInTheBox">
      <p>不要点我可以吗</p>
      <button @click="open = false">麻烦你把我关了</button>
    </div>
  </Teleport>
</template>

<script setup lang="ts">
import { ref,reactive, inject, Teleport } from 'vue'

const count = ref(2)

const open = ref(false)

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

<style scoped>
.modal {
  position: fixed;
  background: pink;
  z-index: 999;
  top: 20%;
  left: 50%;
  width: 300px;
  margin-left: -150px;
}
</style>