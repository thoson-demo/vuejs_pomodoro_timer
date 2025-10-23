<script setup>
import TimerCircle from './TimerCircle.vue'
import TimerControl from './TimerControl.vue'
import { Status } from '../models/Status'
import { ref, onUnmounted } from 'vue'
import { onMounted } from 'vue'

const pomodoroDurationInSecond = 1500 // 25 minutes
const status = ref(Status.Stopped)
const remainTimeInSecond = ref(pomodoroDurationInSecond) // 25 minutes
let timerInterval = null

function onActions(action) {
  console.log('Action received in PomodoroTimer:', action)
  if (action === 'start') {
    console.log('Starting the timer...')
    startPomodoro()
  } else if (action === 'stop') {
    console.log('Stopping the timer...')
    stopPomodoro()
  }
}

function startPomodoro() {
  remainTimeInSecond.value = pomodoroDurationInSecond
  status.value = Status.Running
}

function stopPomodoro() {
  status.value = Status.Stopped
  remainTimeInSecond.value = pomodoroDurationInSecond
}

function onTick() {
  if (status.value === Status.Running && remainTimeInSecond.value > 0) {
    remainTimeInSecond.value -= 1
    console.log('Timer ticked. Remaining time (s):', remainTimeInSecond.value)
    if (remainTimeInSecond.value === 0) {
      console.log('Pomodoro session completed!')
      status.value = Status.Stopped
    }
  }
}

onMounted(() => {
  timerInterval = setInterval(() => {
    onTick()
  }, 1000)
})

onUnmounted(() => {
  if (timerInterval) {
    clearInterval(timerInterval)
  }
})
</script>

<template>
  <div class="pomodoro-container">
    <TimerCircle :remainTimeInSecond="remainTimeInSecond" />
    <TimerControl @actions="onActions" />
  </div>
</template>

<style scoped>
.pomodoro-container {
  width: 300px;
  background: #1e1e1e;
  border: #353535 6px solid;
  border-radius: 16px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
}
</style>
