<script setup lang="ts">
import { ref } from 'vue'
import Cartoon from './alternativeComponents/cartoon.vue'

const cartoons = ref([
  {
    title: 'ThunderCats',
    desc: 'ThunderCats is an American media franchise, featuring a fictional group of cat-like humanoid aliens.',
    votes: { yay: 7, nay: 3 },
  },
  {
    title: 'Captain Planet',
    desc: 'Our world is in peril. Gaia, the spirit of the Earth, can no longer stand the terrible destruction plaguing our planet. She sends five magic rings to five special young people.',
    votes: { yay: 8, nay: 2 },
  },
  {
    title: 'Top Cat',
    desc: 'The title character is the leader of a gang of Manhattan alley cats who constantly hatch get-rich-quick schemes through scams, but most of them usually backfire.',
    votes: { yay: 1, nay: 9 },
  },
  {
    title: "Dexter's Labratory",
    desc: 'The series follows Dexter, an enthusiastic boy-genius with a hidden science laboratory in his room full of inventions, which he keeps secret from his clueless parents.',
    votes: { yay: 6, nay: 4 },
  },
])
</script>
<template>
  <h2 style="color: white">Two-way Data Bind</h2>
  <ol style="color: white">
    <li>
      Changing a reactive variable (e.g., in JavaScript/TypeScript) automatically re-renders the DOM
    </li>
    <li>
      Manipulating a DOM element (e.g., a textbox/slider/etc.) automatically updates a reactive
      variable
    </li>
  </ol>
  <div v-bind:style="{ background: '--background-color', color: 'white' }">
    <p v-for="c in cartoons" :key="c.title">
      <Cartoon v-bind="c" />
    </p>
  </div>
</template>
