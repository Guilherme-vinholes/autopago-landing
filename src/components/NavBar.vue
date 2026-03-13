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
        class="hidden md:flex items-center gap-2 bg-brand-green hover:bg-brand-green-mid text-white font-body font-semibold text-sm px-5 py-2.5 rounded-xl transition-all duration-200 hover:scale-105"
      >
        <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
          <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
        </svg>
        Falar no WhatsApp
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
