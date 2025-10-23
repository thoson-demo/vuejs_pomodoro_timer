<script setup>
import { watch, computed } from 'vue'

const props = defineProps({
  remainTimeInSecond: Number,
})

const remainTimeDisplay = computed(() => {
  const minutes = Math.floor(props.remainTimeInSecond / 60)
  const seconds = props.remainTimeInSecond % 60
  return `${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`
})

watch(remainTimeDisplay, (newVal) => {
  console.log('Counter display updated to:', newVal)
})
</script>

<template>
  <div class="timer-circle-container">
    <div class="timer-circle-border">
      <!-- <h1 class="timer-display">{{ counterDisplay }}</h1> -->
      <h1 class="timer-display" v-text="remainTimeDisplay"></h1>
    </div>
  </div>
</template>
<style scoped>
.timer-circle-container {
  margin: 0;
  padding: 0;
  /* background-color: #1e1e1e; */
  aspect-ratio: 1 / 1;
  display: flex;
  justify-content: center;
  align-items: center;
}
.timer-circle-border {
  width: 200px;
  height: 200px;
  border: 6px solid #efa844;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
}
.timer-display {
  color: white;
  font-size: 40px;
  font-weight: bold;
}
</style>
