<template>
  <div class="min-h-screen bg-brand-black text-brand-text">
    <NavBar />
    <main>
      <HeroSection />
      <ComoFunciona />
      <Beneficios />
      <Planos />
      <FAQ />
      <CTAFooter />
    </main>
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import ComoFunciona from './components/ComoFunciona.vue'
import Beneficios from './components/Beneficios.vue'
import Planos from './components/Planos.vue'
import FAQ from './components/FAQ.vue'
import CTAFooter from './components/CTAFooter.vue'
</script>
