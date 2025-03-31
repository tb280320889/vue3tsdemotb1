<template>
  <div class="person">
    <h2>当前求和为:{{ sum }}</h2>
    <button @click="changeSum">+1</button>
  </div>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue'

let sum = ref(0)

function changeSum() {
  sum.value++
}

//  情况一 监视ref 定义的基本类型数据
const stopWatch = watch(sum, (newValue, oldValue) => {
  console.log('sum变化了 :>> ', newValue + ' == ' + oldValue)
  if (newValue > 10) {
    //watch 返回一个函数,用来控制watch的停止
    stopWatch()
  }
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
