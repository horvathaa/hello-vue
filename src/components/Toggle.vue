<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps<{
  bool: boolean
}>()

const { bool } = props

const isToggled = ref(bool)
const emit = defineEmits<{
  (e: 'update', value: boolean): void
}>()

function toggle() {
  isToggled.value = !isToggled.value
  emit('update', isToggled.value) // emit new state to parent
}
</script>
<template>
  <button @click="toggle">
    {{ isToggled ? 'ON' : 'OFF' }}
  </button>
</template>
<style scoped>
button {
  padding: 0.5rem 1rem;
  border: 1px solid #ccc;
  border-radius: 0.5rem;
  cursor: pointer;
}
button.active {
  background-color: #42b883;
  color: white;
}
</style>
