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
const list = reactive({
  newName: '小菜花',
  desc: '菜花'
})
console.log(list.newName === newName.value) // 解包   
console.log(list) //返回refImpl
console.log(newName)

const changeName =() => {
  if (list.newName === '小菜花') {
    list.newName = '新冠'
  } else if (list.newName === '新冠') {
    list.newName = '小菜花'
  }
  console.log(list.newName)
  console.log(newName)
}
</script>