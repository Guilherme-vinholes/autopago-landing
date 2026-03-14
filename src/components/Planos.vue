<template>
  <section id="nos" class="py-24 px-6 bg-brand-surface/30">
    <div class="max-w-5xl mx-auto">

      <!-- Header -->
      <div class="text-center mb-16">
        <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Quem somos</span>
        <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
          Tecnologia que <span class="text-gradient">gera resultado</span>
        </h2>
        <p class="font-body text-brand-muted mt-4 max-w-2xl mx-auto">
          A AutoPago é uma empresa de tecnologia focada em sistemas SaaS para pequenos e médios negócios.
          Entregamos soluções simples, diretas e que se pagam desde o primeiro cliente.
        </p>
      </div>

      <!-- Clientes -->
      <div class="text-center mb-10">
        <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Quem confia na AutoPago</span>
      </div>

      <div class="grid md:grid-cols-3 gap-6">
        <div
          v-for="(client, i) in clients"
          :key="i"
          class="group flex flex-col items-center text-center p-8 rounded-2xl bg-brand-surface border-glow hover:border-brand-green/30 transition-all duration-300 hover:-translate-y-1"
        >
          <!-- Logo / Iniciais -->
          <div class="w-28 h-28 rounded-2xl overflow-hidden mb-5 flex items-center justify-center">
            <img
              v-if="client.logo"
              :src="client.logo"
              :alt="client.name"
              class="w-full h-full object-contain"
            />
            <span v-else class="font-display font-bold text-2xl text-brand-green/40">{{ client.initials }}</span>
          </div>

          <!-- Nome e segmento -->
          <h3 class="font-display font-bold text-lg text-brand-text mb-1">{{ client.name }}</h3>
          <span class="font-mono text-xs text-brand-green tracking-wider uppercase mb-3">{{ client.segment }}</span>

          <!-- Depoimento -->
          <p class="font-body text-brand-muted text-sm leading-relaxed italic">"{{ client.quote }}"</p>

          <!-- Link -->
          <a
            v-if="client.url"
            :href="client.url"
            target="_blank"
            rel="noopener noreferrer"
            class="font-mono text-xs text-brand-green hover:underline mt-3"
          >{{ client.url }}</a>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const clients = [
  {
    name: 'Limatec MS',
    initials: 'LT',
    segment: 'Tecnologia',
    quote: 'O AutoPago simplificou toda a nossa gestão. Hoje temos controle real do negócio sem complicação.',
    logo: 'https://limatecms.com/img/icon.5717a9e4.svg',
    url: 'https://limatecms.com',
  },
  {
    name: 'Cliente 2',
    initials: 'C2',
    segment: 'Segmento',
    quote: 'Depoimento breve sobre como o AutoPago ajudou o negócio a crescer.',
    logo: '',
    url: 'LINK',
  },
  {
    name: 'Cliente 3',
    initials: 'C3',
    segment: 'Segmento',
    quote: 'Depoimento breve sobre como o AutoPago ajudou o negócio a crescer.',
    logo: '',
    url: 'LINK',
  },
]
</script>
