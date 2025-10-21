<script setup>
import PomodoroTimer from './components/PomodoroTimer.vue'
</script>

<template>
  <div class="app-background">
    <PomodoroTimer />
  </div>
</template>

<style scoped>
.app-background {
  position: fixed;
  top: 0;
  left: 0;
  min-height: 100vh;
  width: 100%;
  background: linear-gradient(-45deg, #d68d37, #090806);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
