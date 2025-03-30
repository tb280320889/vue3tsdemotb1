<template>
  <div class="person">
    <h2>{{ car.name }},{{ car.price }}</h2>
    <button @click="changePrice">修改价格</button>
    <ul>
      <li v-for="game in games" :key="game.id">
        {{ game.name }}
      </li>
    </ul>
    <button @click="changeFirstGame">修改第一个游戏的名字</button>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue'
let car = reactive({ name: 'car', price: 1000 })

let games = reactive([
  { id: '11', name: 'wz' },
  { id: '22', name: 'ys' },
  { id: '33', name: 'lol' },
])

function changeFirstGame() {
  games[0].name = 'wzry'
}

function changePrice() {
  car.price += 1
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
