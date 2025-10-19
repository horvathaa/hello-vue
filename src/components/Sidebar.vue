<script lang="ts">
export default {
  name: 'Sidebar',
}
</script>
<template>
  <!-- <aside class="sidebar"> -->
  <nav class="sidebar">
    <ul>
      <li><a href="#introduction">Introduction</a></li>
      <li><a href="#getting-started">Getting Started</a></li>
      <li><a href="#features">Features</a></li>
      <li><a href="#installation">Installation</a></li>
      <li><a href="#usage">Usage</a></li>
      <li><a href="#contributing">Contributing</a></li>
      <li><a href="#license">License</a></li>
    </ul>
  </nav>
  <!-- </aside> -->
</template>
<style scoped>
.sidebar {
  width: 250px;
  padding: 1rem;
  background-color: var(--color-sidebar-background);
  border-right: 1px solid var(--color-border);
}
nav ul {
  list-style: none;
  padding: 0;
}
nav li {
  margin: 0.5rem 0;
}
nav a {
  text-decoration: none;
  color: var(--color-link);
}
nav a:hover {
  text-decoration: underline;
}
</style>
