<template>
  <div class="person">
    <h1>情况三: 监视 `reactive` 定义的 '对象类型' 数据</h1>
    <h2>姓名 : {{ person.name }}</h2>
    <h2>年龄 : {{ person.age }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="changePerson">修改人</button>
  </div>
</template>

<script setup lang="ts">
import { reactive, ref, watch } from 'vue'

let person = reactive({
  name: '张三',
  age: 18,
})

function changeName() {
  person.name += '~'
}
function changeAge() {
  person.age += 1
}
function changePerson() {
  Object.assign(person, { name: 'wang-wu', age: 20 })
}

//监视 情况三 : 监视[reactive]定义的响应式对象,隐式创建了不可关闭的深层监听
watch(person, (newValue, oldValue) => {
  console.log('person', newValue, oldValue)
})
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
