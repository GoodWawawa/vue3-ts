<template>
<p>{{ list.newName }}</p>
<button @click="changeName">改名字</button>
</template>

<script lang="ts" setup>
import { ref, reactive } from 'vue'
const list1 = reactive({g: 'hao'})
console.log(list1)  //返回proxy对象
console.log(list1.g)
const newName = ref('小菜花')   
//reactive 创建一个响应式的对象
const list = reactive({ newName })
console.log(list.newName === newName.value) // 解包   
console.log(list) //返回refImpl
console.log(newName)

const changeName =() => {
  newName.value = '新冠'
  console.log(list.newName)
  console.log(newName)
}
</script>