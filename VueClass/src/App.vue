<script setup>
import { ref } from 'vue'

let notifications = ref(0)

function minusValue() {
  if (notifications.value <= 0) {
    return
  }

  notifications.value--
  console.log(notifications)
}
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="photo"></div>
      <div class="dot" v-if="notifications > 0">{{ notifications }}</div>
    </div>
    <div class="buttons">
      <div @click="minusValue">-</div>
      <div @click="notifications++">+</div>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  background-color: aliceblue;
  display: grid;
  place-items: center;
  width: 400px;
  margin: auto;
  user-select: none;
}

.profile {
  position: relative;
  margin-top: 30px;
}
.photo {
  background-image: url('https://images.unsplash.com/photo-1632929541783-b67da9cd462c?auto=format&fit=crop&q=60&w=500&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTZ8fGVtcGFuYWRhfGVufDB8fDB8fHww');
  display: block;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-size: cover;
}

.dot {
  --size: 30px;

  background-color: blanchedalmond;
  display: block;
  width: var(--size);
  height: var(--size);
  position: absolute;
  top: -10px;
  right: -10px;
  border-radius: 50%;
  text-align: center;
  line-height: var(--size);
}

.buttons {
  display: flex;
  height: 50px;
  align-items: center;
  justify-content: space-around;
  width: 100%;
}

.buttons div {
  background-color: blanchedalmond;
  display: block;
  width: 60px;
  height: 30px;
  border-radius: 15px;
  text-align: center;
  line-height: 30px;
  font-size: 20;
  font-weight: bolder;
  cursor: pointer;
}
</style>
