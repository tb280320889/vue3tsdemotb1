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
let a = 666
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
