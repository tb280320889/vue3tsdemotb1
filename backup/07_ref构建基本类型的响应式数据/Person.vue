<template>
  <div class="person">
    <h2>
      <div>姓名：{{ name }}</div>
      <div>年龄：{{ age }}</div>
      <!-- <div>电话：{{ tel }}</div> -->
      <button @click="changeName">修改名字</button>
      <button @click="changeAge">修改年龄</button>
      <button @click="showTel">查看联系方式</button>
    </h2>
  </div>
</template>

<script setup lang="ts">
import { ref, defineOptions } from 'vue'

let name = ref('张三') // 此时name不是响应式
let age = ref(18) // 此时age不是响应式
let tel = '138888888' // 此时tel不是响应式
function changeName() {
  name.value = '李四'
  console.log('1 :>> ', 1)
}
function changeAge() {
  age.value += 1
  console.log('2 :>> ', 2)
}
function showTel() {
  alert(tel)
  console.log('3 :>> ', 3)
}

defineOptions({ name: 'Person' })
</script>

<style scoped>
.person {
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
button {
  margin: 10px;
}
</style>
