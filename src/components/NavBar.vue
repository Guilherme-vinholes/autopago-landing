<template>
  <nav
    :class="[
      'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
      scrolled ? 'bg-black/60 backdrop-blur-md border-b border-white/10' : 'bg-black/60 backdrop-blur-md'
    ]"
  >
    <div class="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
      <!-- Logo -->
      <a href="#" class="flex items-center gap-1 group">
        <img src="/logo_ap2.png" alt="Autopago" class="h-12 w-auto" />
        <span class="font-display font-bold text-2xl text-white">
          Auto<span class="text-brand-green">pago</span>
        </span>
      </a>

      <!-- Desktop Nav -->
      <div class="hidden md:flex items-center gap-8">
        <a href="#nos" class="text-white/60 hover:text-white text-sm font-body transition-colors duration-200">Nós</a>
        <a href="#autosystem" class="text-white/60 hover:text-white text-sm font-body transition-colors duration-200">AutoSystem</a>
        <a href="#contato" class="text-white/60 hover:text-white text-sm font-body transition-colors duration-200">Contate-nos</a>
      </div>

      <!-- CTA Button -->
      <a
        :href="whatsappUrl"
        target="_blank"
        rel="noopener noreferrer"
        class="hidden md:flex items-center font-body font-semibold text-sm px-5 py-2.5 rounded-xl transition-all duration-200 hover:scale-105 hover:brightness-90"
        style="background-color: #4ae8af; color: #07090D;"
      >
        Fale com especialista
      </a>

      <!-- Mobile Menu Button -->
      <button
        @click="mobileOpen = !mobileOpen"
        class="md:hidden p-2 text-white/60 hover:text-white transition-colors"
        aria-label="Menu"
      >
        <svg v-if="!mobileOpen" class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
        <svg v-else class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    <div
      v-if="mobileOpen"
      class="md:hidden bg-brand-surface/95 backdrop-blur-md border-t border-white/5 px-6 py-4 flex flex-col gap-4"
    >
      <a href="#nos" @click="mobileOpen = false" class="text-white/60 hover:text-white text-sm font-body py-2 transition-colors">Nós</a>
      <a href="#autosystem" @click="mobileOpen = false" class="text-white/60 hover:text-white text-sm font-body py-2 transition-colors">AutoSystem</a>
      <a href="#contato" @click="mobileOpen = false" class="text-white/60 hover:text-white text-sm font-body py-2 transition-colors">Contate-nos</a>
      <a
        :href="whatsappUrl"
        target="_blank"
        rel="noopener noreferrer"
        class="flex items-center justify-center gap-2 bg-brand-green text-brand-black font-semibold text-sm px-5 py-3 rounded-xl mt-2"
      >
        Falar no WhatsApp
      </a>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const scrolled = ref(false)
const mobileOpen = ref(false)
const whatsappUrl = 'https://wa.me/5514999999999?text=Ol%C3%A1%2C%20quero%20saber%20mais%20sobre%20o%20Autopago!'

const handleScroll = () => {
  scrolled.value = window.scrollY > 20
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>
