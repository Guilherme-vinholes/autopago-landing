<template>
  <section class="relative min-h-screen flex items-center justify-center overflow-hidden pt-20">

    <!-- Video background -->
    <video
      src="/banner.mp4"
      autoplay
      loop
      muted
      playsinline
      class="absolute inset-0 w-full h-full object-cover"
    ></video>

    <!-- Overlay escuro para legibilidade -->
    <div class="absolute inset-0 bg-black/80"></div>

    <!-- Content -->
    <div class="relative z-10 max-w-5xl mx-auto px-6 text-center">

      <!-- Badge -->
      <div
        class="inline-flex items-center gap-2 bg-white/10 backdrop-blur-sm border border-white/20 rounded-full px-3 py-1.5 mb-6 opacity-0 animate-fade-up"
        style="animation-fill-mode: forwards;"
      >
        <span class="w-2 h-2 rounded-full bg-brand-green animate-pulse flex-shrink-0"></span>
        <span class="font-mono text-xs text-white/70 tracking-wider uppercase">Sistemas · SaaS · Soluções Empresariais</span>
      </div>

      <!-- Headline -->
      <h1
        class="font-display font-extrabold text-2xl sm:text-3xl md:text-4xl leading-tight tracking-tight mb-6 opacity-0 animate-fade-up delay-100 text-white text-center w-full"
        style="animation-fill-mode: forwards; min-height: 1.4em;"
      >
        <span>{{ part1 }}</span><span class="text-gradient">{{ part2 }}</span><span class="text-brand-green animate-pulse">|</span>
      </h1>

      <!-- Subheadline -->
      <p
        class="font-body text-base md:text-xl text-white/70 max-w-2xl mx-auto mb-4 leading-relaxed opacity-0 animate-fade-up delay-200 px-2"
        style="animation-fill-mode: forwards;"
      >
        Tecnologia pensada para o seu negócio crescer —
        <strong class="text-white font-medium">simples, direta e eficiente.</strong>
      </p>

      <!-- ROI highlight -->
      <div
        class="inline-flex items-center gap-2 bg-white/10 backdrop-blur-sm border border-white/20 rounded-2xl px-4 py-2.5 mb-8 opacity-0 animate-fade-up delay-300"
        style="animation-fill-mode: forwards;"
      >
        <span class="font-mono text-brand-green text-sm flex-shrink-0">ROI →</span>
        <span class="font-body text-white text-sm">Retorno garantido desde o primeiro mês de uso</span>
      </div>

      <!-- CTAs -->
      <div
        class="flex flex-col sm:flex-row items-center justify-center gap-3 opacity-0 animate-fade-up delay-400 w-full px-4 sm:px-0"
        style="animation-fill-mode: forwards;"
      >
        <a
          :href="whatsappUrl"
          target="_blank"
          rel="noopener noreferrer"
          class="w-full sm:w-auto font-body font-semibold px-8 py-4 rounded-2xl transition-all duration-300 hover:scale-105 hover:brightness-90 text-base text-center"
          style="background-color: #4ae8af; color: #07090D;"
        >
          Conheça o AutoPago
        </a>

        <a
          href="#como-funciona"
          class="w-full sm:w-auto flex items-center justify-center gap-2 text-white/60 hover:text-white font-body text-sm px-6 py-4 rounded-2xl border border-white/20 hover:border-white/40 transition-all duration-200"
        >
          Ver como funciona
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
          </svg>
        </a>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 animate-float opacity-60">
      <svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
      </svg>
    </div>
  </section>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const whatsappUrl = 'https://wa.me/5514991373142?text=Ol%C3%A1%2C%20quero%20saber%20mais%20sobre%20o%20Autopago!'

const LINE1 = 'Onde custo '
const FULL  = 'Onde custo vira resultado.'

const displayText = ref('')
let timer = null

const part1 = computed(() => {
  return displayText.value.slice(0, Math.min(displayText.value.length, LINE1.length))
})
const part2 = computed(() => {
  if (displayText.value.length <= LINE1.length) return ''
  return displayText.value.slice(LINE1.length)
})

const sleep = (ms) => new Promise(r => { timer = setTimeout(r, ms) })

const run = async () => {
  while (true) {
    // type
    for (let i = 0; i <= FULL.length; i++) {
      displayText.value = FULL.slice(0, i)
      await sleep(160)
    }
    await sleep(2500)
    // delete
    for (let i = FULL.length; i >= 0; i--) {
      displayText.value = FULL.slice(0, i)
      await sleep(100)
    }
    await sleep(800)
  }
}

onMounted(() => run())
onUnmounted(() => clearTimeout(timer))
</script>
