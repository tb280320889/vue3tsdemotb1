<template>
  <div class="person">
    姓: <input type="text" v-model="firstName" /><br />
    名: <input type="text" v-model="lastName" /><br />
    全名: <span>{{ fullName }}</span>
    <button @click="changeFullName">修改全名</button>
  </div>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue'

let firstName = ref('zhang')
let lastName = ref('san')

//这么定义的computed是只读的
// let fullName = computed(() => {
//   console.log('1 :>> ', 1)
//   return firstName.value.slice(0, 1) + firstName.value.slice(1) + '-' + lastName.value
// })

//定义可读可写的computed
let fullName = computed({
  get() {
    return firstName.value.slice(0, 1) + firstName.value.slice(1) + '-' + lastName.value
  },
  set(newValue) {
    const [str1, str2] = newValue.split('-')
    firstName.value = str1
    lastName.value = str2
  },
})

function changeFullName() {
  fullName.value = 'wang-wu'
}
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
