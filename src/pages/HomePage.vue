<template>
  <div>
    <HeroSection />
    <ComoFunciona />
    <Beneficios />
    <Planos />
    <FAQ />
    <CTAFooter @navigate="(page) => $emit('navigate', page)" />
  </div>
</template>

<script setup>
defineEmits(['navigate'])
import HeroSection from '../components/HeroSection.vue'
import ComoFunciona from '../components/ComoFunciona.vue'
import Beneficios from '../components/Beneficios.vue'
import Planos from '../components/Planos.vue'
import FAQ from '../components/FAQ.vue'
import CTAFooter from '../components/CTAFooter.vue'
</script>
