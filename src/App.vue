<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import Sidebar from './components/Sidebar.vue'
import Toggle from './components/Toggle.vue'
import { ref } from 'vue'
import Alternative from './components/Alternative.vue'

const isDefaultLayout = ref(true)
function handleToggle(value: boolean) {
  isDefaultLayout.value = value
}
</script>

<template>
  <div class="sidebar">
    <Toggle :bool="false" />
    <Sidebar />
  </div>

  <header v-if="isDefaultLayout">
    <div class="wrapper">
      <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main v-if="isDefaultLayout">
    <Toggle :bool="isDefaultLayout" v-on:update="handleToggle" />
    <TheWelcome />
  </main>
  <main v-else>
    <Toggle :bool="isDefaultLayout" v-on:update="handleToggle" />
    <Alternative />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.sidebar {
  margin-bottom: 2rem;
  display: flex;
  padding: 1rem;
  flex-direction: column;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    flex-direction: column;
    place-items: flex-start;
    flex-wrap: wrap;
    margin: 1rem;
  }
}
</style>
