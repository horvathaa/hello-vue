<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps<{
  bool: boolean
}>()

const { bool } = props

const isToggled = ref(bool)
</script>
<template>
  <button @click="isToggled = !isToggled">
    {{ isToggled ? 'ON' : 'OFF' }}
  </button>
</template>
<style scoped>
button {
  padding: 0.5rem 1rem;
  font-size: 1rem;
  border: none;
  border-radius: 4px;
  background-color: var(--color-primary);
  color: white;
  cursor: pointer;
}
</style>
