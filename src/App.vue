<script setup>
import { onMounted, onUnmounted, ref } from 'vue';
import ArtSection from './components/ArtSection.vue'
</script>

<template>
  <div class='h-full w-full flex flex-col'>
    <header class='flex justify-center flex-col text-8xl'>
      <h1>Art</h1>
      <span>by Lucien</span>
    </header>
    <main class='grow'>
      <ArtSection hash='1'>
        <div class='block'></div>
      </ArtSection>
      <ArtSection hash='2'>
        <div class='bg-gray-600 w-1/2 h-1/2'>
          <div class='bg-red-300 w-1/2 h-1/2'>
            <span class='font-black text-orange-800'>Hi</span>
          </div>
        </div>
      </ArtSection>
      <ArtSection hash='3'>
        <div class='h-full w-full flex content-center'>
          <span
            class='text-9xl font-bold bg-clip-text from-orange-400 to-red-400 text-transparent bg-gradient-to-tr'>Smooth</span>
        </div>
      </ArtSection>
    </main>
  </div>
</template>

<style scoped>
.block {
  background-color: red;
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
  width: 50%;
  justify-self: center;
}

.block:hover {
  filter: saturate(0.5) brightness(1.2);
}
</style>
