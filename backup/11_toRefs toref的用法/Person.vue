<template>
  <div class="person">
    <h2>姓名:{{ person.name }}</h2>
    <h2>年龄:{{ person.age }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">年龄加1</button>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive, toRefs, toRef } from 'vue'

let person = reactive({
  name: '张三',
  age: 18,
})

let { name, age } = toRefs(person)

let age2 = toRef(person, 'age')

function changeName() {
  name.value = '李四'
}

function changeAge() {
  age2.value++
}
</script>

<style scoped></style>
