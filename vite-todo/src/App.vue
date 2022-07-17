<script setup lang="ts">
import TodoContainer from './components/TodoContainer.vue'

import vue from './assets/vue.svg'
</script>

<template>
  <div class="flex justify-center">
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo bg-cover bg-center" alt="Vite logo" />
    </a>
  </div>
  <TodoContainer/>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
</style>
