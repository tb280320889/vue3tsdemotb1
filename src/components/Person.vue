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
  data() {
    return {
      name: '张三',
      age: 18,
      tel: '138888888',
    }
  },
  methods: {
    changeName() {
      this.name = '李四--'
    },
    changeAge() {
      this.age += 1
    },
    showTel() {
      alert(this.tel)
    },
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
