<template>
  <div class="person">
    <h1>情况二: 监视 `ref` 定义的 '对象类型' 数据</h1>
    <h2>姓名 : {{ person.name }}</h2>
    <h2>年龄 : {{ person.age }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="changePerson">修改人</button>
  </div>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue'

let person = ref({
  name: '张三',
  age: 18,
})

function changeName() {
  person.value.name += '~'
}
function changeAge() {
  person.value.age += 1
}
function changePerson() {
  person.value = {
    name: '李四',
    age: 20,
  }
}

//监视 情况1 : 监视 ref定义的 对象类型的数据,监视的对象的地址值,假如想监视对象内部属性的变化,需要手动添加配置项
watch(
  person,
  (newValue, oldValue) => {
    console.log('person', newValue, oldValue)
  },
  { deep: true, immediate: true },
)
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
