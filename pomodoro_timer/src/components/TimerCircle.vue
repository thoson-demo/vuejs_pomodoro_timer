<script setup>
import { computed } from 'vue'

const props = defineProps({
  progress: {
    type: Number,
    default: 0,
  },
  total: {
    type: Number,
    default: 1,
  },
})

// SVG circle properties - responsive
const radius = computed(() => 90) // Để margin cho stroke
const circumference = computed(() => 2 * Math.PI * radius.value)

// Tính stroke-dashoffset từ percent (0-1)
const strokeDashoffset = computed(() => {
  return circumference.value - (props.progress / props.total) * circumference.value
})
</script>

<template>
  <div class="timer-circle-container">
    <svg class="timer-svg" viewBox="0 0 200 200">
      <!-- Background circle -->
      <circle cx="100" cy="100" :r="radius" fill="none" stroke="#353535" stroke-width="6" />
      <!-- Progress circle -->
      <circle
        cx="100"
        cy="100"
        :r="radius"
        fill="none"
        stroke="#efa844"
        stroke-width="6"
        :stroke-dasharray="circumference"
        :stroke-dashoffset="strokeDashoffset"
        stroke-linecap="round"
        transform="rotate(-90 100 100)"
        class="progress-circle"
      />
    </svg>
    <div class="timer-content">
      <slot>Time display</slot>
    </div>
  </div>
</template>

<style scoped>
.timer-circle-container {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.timer-svg {
  width: 100%;
  height: 100%;
  max-width: 100%;
  max-height: 100%;
}

.timer-content {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 2;
}

.progress-circle {
  transition: stroke-dashoffset 0.3s ease-in-out;
}
</style>
