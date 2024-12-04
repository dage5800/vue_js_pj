<script setup>
import { ref, computed } from 'vue'
import Grid from './components/Grid.vue'
import NotFound from './components/NotFound.vue'

const routes = {
  '/': Grid,
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})
</script>

<template>
  <a href="#/">Grid</a> |
  <a href="#/non-existent-path">Broken Link</a>
  <component :is="currentView" />
</template>