<template>
  <section id="como-funciona" class="py-24 px-6 relative">
    <div class="max-w-5xl mx-auto">

      <!-- Section header -->
      <div class="text-center mb-16">
        <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Como funciona</span>
        <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
          Simples do começo ao fim
        </h2>
        <p class="font-body text-brand-muted mt-4 max-w-xl mx-auto">
          Em poucos passos, seu negócio já está rodando com tecnologia que gera retorno real.
        </p>
      </div>

      <!-- Steps -->
      <div class="relative">
        <!-- Connector line (desktop) -->
        <div class="hidden md:block absolute top-12 left-0 right-0 h-px bg-gradient-to-r from-transparent via-brand-green/30 to-transparent"></div>

        <div class="grid md:grid-cols-3 gap-8">
          <div
            v-for="(step, i) in steps"
            :key="i"
            class="relative flex flex-col items-center text-center group"
          >
            <!-- Step number -->
            <div class="relative mb-6">
              <div class="w-24 h-24 rounded-2xl bg-brand-surface border-glow flex items-center justify-center transition-all duration-300 group-hover:glow-green group-hover:border-brand-green/40 z-10 relative">
                <span class="text-3xl">{{ step.icon }}</span>
              </div>
              <div class="absolute -top-2 -right-2 w-6 h-6 rounded-full bg-brand-green flex items-center justify-center z-20">
                <span class="font-mono text-xs font-bold text-brand-black">{{ i + 1 }}</span>
              </div>
            </div>

            <h3 class="font-display font-bold text-xl text-brand-text mb-3">{{ step.title }}</h3>
            <p class="font-body text-brand-muted text-sm leading-relaxed">{{ step.description }}</p>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const steps = [
  {
    icon: '🤝',
    title: 'Você contrata',
    description: 'Plano simples, preço justo. Nenhuma pegadinha. Você entende exatamente o que está pagando antes de assinar.',
  },
  {
    icon: '⚙️',
    title: 'Configuramos juntos',
    description: 'Nossa equipe ativa o sistema e adapta os módulos ao seu negócio. Suporte humano do início ao fim.',
  },
  {
    icon: '📈',
    title: 'Seu negócio cresce',
    description: 'O primeiro cliente que você fechar já paga a mensalidade. A partir daí, é lucro puro.',
  },
]
</script>
