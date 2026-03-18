<template>
  <nav class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 bg-black/60 backdrop-blur-md">
    <div class="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
      <!-- Logo -->
      <a href="javascript:void(0)" @click.prevent="router.push('/')" class="flex items-center gap-1 group cursor-pointer">
        <img src="/logo_ap2.png" alt="Autopago" class="h-12 w-auto" />
        <span class="font-display font-bold text-2xl text-white">
          Auto<span class="text-brand-green">pago</span>
        </span>
      </a>

      <!-- Desktop Nav -->
      <div class="hidden md:flex items-center gap-8">
        <a href="javascript:void(0)" @click.prevent="router.push('/NossoSistema')" class="text-white/60 hover:text-white text-sm font-body transition-colors duration-200 cursor-pointer">Nosso Sistema</a>
        <a href="javascript:void(0)" @click.prevent="handleAnchor('#nos')" class="text-white/60 hover:text-white text-sm font-body transition-colors duration-200 cursor-pointer">Quem Somos?</a>
        <a href="javascript:void(0)" @click.prevent="handleAnchor('#contato')" class="text-white/60 hover:text-white text-sm font-body transition-colors duration-200 cursor-pointer">Contate-nos</a>
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
    <transition name="mobile-menu">
      <div
        v-if="mobileOpen"
        class="md:hidden bg-black/90 backdrop-blur-md border-t border-white/10 px-6 py-6 flex flex-col gap-1"
      >
        <a href="javascript:void(0)" @click.prevent="router.push('/NossoSistema'); mobileOpen = false" class="text-white/70 hover:text-white text-base font-body py-3 border-b border-white/10 transition-colors">Nosso Sistema</a>
        <a href="javascript:void(0)" @click.prevent="handleAnchor('#nos'); mobileOpen = false" class="text-white/70 hover:text-white text-base font-body py-3 border-b border-white/10 transition-colors">Quem Somos?</a>
        <a href="javascript:void(0)" @click.prevent="handleAnchor('#contato'); mobileOpen = false" class="text-white/70 hover:text-white text-base font-body py-3 border-b border-white/10 transition-colors">Contate-nos</a>
        <a
          :href="whatsappUrl"
          target="_blank"
          rel="noopener noreferrer"
          class="flex items-center justify-center font-body font-semibold text-sm px-5 py-3.5 rounded-xl mt-4 transition-all hover:brightness-90"
          style="background-color: #4ae8af; color: #07090D;"
        >
          Fale com especialista
        </a>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted, nextTick } from 'vue'
import { useRouter, useRoute } from 'vue-router'

const router = useRouter()
const route = useRoute()

const handleAnchor = async (hash) => {
  if (route.path === '/') {
    const el = document.querySelector(hash)
    if (el) el.scrollIntoView({ behavior: 'smooth' })
  } else {
    await router.push('/')
    await nextTick()
    setTimeout(() => {
      const el = document.querySelector(hash)
      if (el) el.scrollIntoView({ behavior: 'smooth' })
    }, 100)
  }
}

const mobileOpen = ref(false)
const whatsappUrl = 'https://wa.me/5514991373142?text=Ol%C3%A1%2C%20quero%20saber%20mais%20sobre%20o%20Autopago!'

const handleScroll = () => {}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: opacity 0.2s ease, transform 0.2s ease;
}
.mobile-menu-enter-from,
.mobile-menu-leave-to {
  opacity: 0;
  transform: translateY(-8px);
}
</style>
