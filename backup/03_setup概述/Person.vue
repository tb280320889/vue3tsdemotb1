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
<script lang="ts">
export default {
  name: 'Person',

  setup() {
    //setup 中的this是undefined,vue3已经开始弱化this
    //数据原来是写在data中的，此时的name，age，tel都不是响应式的数据
    let name = '张三' // 此时name不是响应式
    let age = 18 // 此时age不是响应式
    let tel = '138888888' // 此时tel不是响应式
    function changeName() {
      name = '李四'
      console.log('1 :>> ', 1)
    }
    function changeAge() {
      age += 1
      console.log('2 :>> ', 2)
    }
    function showTel() {
      alert(tel)
      console.log('2 :>> ', 3)
    }

    return {
      name,
      age,
      tel,
      changeName,
      changeAge,
      showTel,
    }
  },
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
