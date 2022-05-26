<template>

</template>

<script lang="ts" setup>
import { ref, computed } from 'vue'

//相当于get 只读
const Num = ref(2)
const List = computed(() => Num.value + 1)
console.log(List.value)

//可写
const Num1 = ref(3)
const List1 = computed({
  get: () => Num1.value + 1,
  set: (val) => {
    Num1.value = val + 1
    console.log('我走了这里')
  }
})

List1.value = 4
console.log(Num1.value)
console.log(List1.value)

</script>