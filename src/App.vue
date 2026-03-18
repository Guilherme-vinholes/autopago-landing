<template>
  <div class="min-h-screen bg-brand-black text-brand-text">
    <NavBar />
    <main>
      <RouterView />
    </main>
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue'
</script>
