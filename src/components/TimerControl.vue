<script setup>
import { defineEmits } from 'vue'

const emit = defineEmits(['actions'])

function start() {
  emit('actions', 'start')
  console.log('Start clicked')
}

function stop() {
  emit('actions', 'stop')
  console.log('Stop clicked')
}
</script>

<template>
  <div class="timer-control-container">
    <button class="button-filled" v-on:click="start">Start</button>
    <button class="button-outlined" @click="stop">Stop</button>
  </div>
</template>
<style scoped>
.timer-control-container {
  padding: 0;
  display: flex;
  gap: 16px;
  justify-content: center;
  align-items: center;
}
.button-filled {
  background-color: #efa844;
  border: 2px solid #efa844;
  border-radius: 8px;
  color: black;
  font-size: 24px;
  font-weight: bold;
  padding: 8px 12px;
  cursor: pointer;
}
.button-outlined {
  background-color: transparent;
  border: 2px solid #ffffff;
  border-radius: 8px;
  color: #ffffff;
  font-size: 24px;
  font-weight: bold;
  padding: 8px 12px;
  cursor: pointer;
}
</style>
