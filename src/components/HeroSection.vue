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
        class="inline-flex items-center gap-2 bg-white/10 backdrop-blur-sm border border-white/20 rounded-full px-4 py-2 mb-8 opacity-0 animate-fade-up"
        style="animation-fill-mode: forwards;"
      >
        <span class="w-2 h-2 rounded-full bg-brand-green animate-pulse"></span>
        <span class="font-mono text-xs text-white/70 tracking-widest uppercase">Sistemas · SaaS · Soluções Empresariais</span>
      </div>

      <!-- Headline -->
      <h1
        class="font-display font-extrabold text-5xl md:text-7xl lg:text-8xl leading-none tracking-tight mb-6 opacity-0 animate-fade-up delay-100 text-white"
        style="animation-fill-mode: forwards; min-height: 1.2em;"
      >
        <span>{{ part1 }}</span>
        <template v-if="showBreak"><br /></template>
        <span class="text-gradient">{{ part2 }}</span><span class="text-brand-green animate-pulse">|</span>
      </h1>

      <!-- Subheadline -->
      <p
        class="font-body text-lg md:text-xl text-white/70 max-w-2xl mx-auto mb-4 leading-relaxed opacity-0 animate-fade-up delay-200"
        style="animation-fill-mode: forwards;"
      >
        Tecnologia pensada para o seu negócio crescer —
        <strong class="text-white font-medium">simples, direta e eficiente.</strong>
      </p>

      <!-- ROI highlight -->
      <div
        class="inline-flex items-center gap-3 bg-white/10 backdrop-blur-sm border border-white/20 rounded-2xl px-5 py-3 mb-10 opacity-0 animate-fade-up delay-300"
        style="animation-fill-mode: forwards;"
      >
        <span class="font-mono text-brand-green text-sm">ROI →</span>
        <span class="font-body text-white text-sm">1 cliente já cobre a mensalidade inteira</span>
      </div>

      <!-- CTAs -->
      <div
        class="flex flex-col sm:flex-row items-center justify-center gap-4 opacity-0 animate-fade-up delay-400"
        style="animation-fill-mode: forwards;"
      >
        <a
          :href="whatsappUrl"
          target="_blank"
          rel="noopener noreferrer"
          class="group flex items-center gap-3 bg-brand-green hover:bg-brand-green-mid text-white font-body font-semibold px-8 py-4 rounded-2xl transition-all duration-300 hover:scale-105 glow-green text-base"
        >
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
          </svg>
          Quero conhecer o Autopago
        </a>

        <a
          href="#como-funciona"
          class="flex items-center gap-2 text-white/60 hover:text-white font-body text-sm px-6 py-4 rounded-2xl border border-white/20 hover:border-white/40 transition-all duration-200"
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

const whatsappUrl = 'https://wa.me/5514999999999?text=Ol%C3%A1%2C%20quero%20saber%20mais%20sobre%20o%20Autopago!'

const LINE1 = 'Onde custo'
const FULL  = 'Onde custo\nvira resultado.'

const displayText = ref('')
let timer = null

const part1 = computed(() => {
  return displayText.value.slice(0, Math.min(displayText.value.length, LINE1.length))
})
const showBreak = computed(() => displayText.value.length > LINE1.length)
const part2 = computed(() => {
  if (displayText.value.length <= LINE1.length + 1) return ''
  return displayText.value.slice(LINE1.length + 1)
})

const sleep = (ms) => new Promise(r => { timer = setTimeout(r, ms) })

const run = async () => {
  while (true) {
    // type
    for (let i = 0; i <= FULL.length; i++) {
      displayText.value = FULL.slice(0, i)
      await sleep(120)
    }
    await sleep(2200)
    // delete
    for (let i = FULL.length; i >= 0; i--) {
      displayText.value = FULL.slice(0, i)
      await sleep(65)
    }
    await sleep(600)
  }
}

onMounted(() => run())
onUnmounted(() => clearTimeout(timer))
</script>
