<template>
  <section id="beneficios" class="py-24 px-6 bg-brand-surface/30">
    <div class="max-w-5xl mx-auto">

      <div class="text-center mb-16">
        <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Benefícios</span>
        <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
          Tecnologia que <span class="text-gradient">justifica o investimento</span>
        </h2>
        <p class="font-body text-brand-muted mt-4 max-w-xl mx-auto">
          Cada funcionalidade foi pensada para gerar valor real, não para impressionar em demo.
        </p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(benefit, i) in benefits"
          :key="i"
          :class="[
            'group p-6 rounded-2xl bg-brand-surface border-glow hover:border-brand-green/30 transition-all duration-300 hover:-translate-y-1',
            benefit.highlight ? 'md:col-span-2 lg:col-span-1 border border-brand-green/20 bg-brand-green/5' : ''
          ]"
        >
          <div class="w-12 h-12 rounded-xl bg-brand-green/10 flex items-center justify-center mb-4 group-hover:bg-brand-green/20 transition-colors">
            <span class="text-xl">{{ benefit.icon }}</span>
          </div>
          <h3 class="font-display font-semibold text-lg text-brand-text mb-2">{{ benefit.title }}</h3>
          <p class="font-body text-brand-muted text-sm leading-relaxed">{{ benefit.description }}</p>
          <div v-if="benefit.tag" class="mt-4">
            <span class="font-mono text-xs text-brand-green bg-brand-green/10 px-3 py-1 rounded-full">{{ benefit.tag }}</span>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const benefits = [
  {
    icon: '💰',
    title: 'ROI Imediato',
    description: 'Um único cliente do seu contratante já cobre a mensalidade do sistema. Risco zero na decisão de contratar.',
    tag: 'plano_mensal → R$ 200/mês',
    highlight: true,
  },
  {
    icon: '📊',
    title: 'Escalável por natureza',
    description: 'Quanto mais o negócio do cliente cresce, mais o sistema se justifica. Cresce junto com você.',
  },
  {
    icon: '🔒',
    title: 'Cobrança transparente',
    description: 'Sem surpresas na fatura. O cliente entende o valor antes mesmo de assinar o contrato.',
  },
  {
    icon: '🧩',
    title: '6 módulos integrados',
    description: 'Gestão, financeiro, clientes, automações e mais — tudo no mesmo sistema, sem integrações complexas.',
    tag: 'status: ativo',
  },
  {
    icon: '🚀',
    title: 'Onboarding rápido',
    description: 'Seu sistema no ar em dias, não meses. Suporte dedicado na configuração inicial.',
  },
  {
    icon: '🤖',
    title: 'Automações inteligentes',
    description: 'Reduza tarefas manuais com automações que trabalham enquanto você dorme.',
  },
]
</script>
