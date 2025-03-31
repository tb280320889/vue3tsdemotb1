<template>
  <div class="person">
    <h2>姓名:{{ person.name }}</h2>
    <h2>年龄:{{ person.age }}</h2>
    <h2>车:{{ person.car.c1 }} ` - `{{ person.car.c2 }}</h2>
    <button @click="changeName">修改姓名</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="changeC1">修改c1</button>
    <button @click="changeC2">修改c2</button>
    <button @click="changeCar">修改整个Car</button>
  </div>
</template>

<script setup lang="ts">
import { reactive, ref, watch } from 'vue'

//数据
let person = reactive({
  name: '张三',
  age: 18,
  car: {
    c1: 'c1',
    c2: 'c2',
  },
})

//方法
function changeName() {
  person.name += '~'
}
function changeAge() {
  person.age += 1
}
function changeC1() {
  person.car.c1 = 'c1-new'
}
function changeC2() {
  person.car.c2 = 'c2-new'
}

function changeCar() {
  person.car = {
    c1: 'c1-new1',
    c2: 'c2-new2',
  }
}
//监视,情况四 : 监视响应式对象的某个属性,且该属性是基本类型
//监视,情况五 : 监视响应式对象的某个属性,且该属性是对象类型的,可以直接写,也能写函数,更推荐写函数
watch(
  () => person.car,
  (newValue, oldValue) => {
    console.log('car', newValue, oldValue)
  },
  {
    deep: true,
  },
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
