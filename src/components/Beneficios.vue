<template>
  <section id="beneficios" class="py-24 px-6 bg-brand-surface/30">
    <div class="max-w-5xl mx-auto">

      <div class="text-center mb-16">
        <span class="font-mono text-brand-green tracking-widest uppercase" style="font-size: 28px;">AutoPago</span>
        <p class="font-body text-brand-muted mt-4 max-w-xl mx-auto">
          Sistema de gestão e relacionamento com o cliente — simples, integrado e feito para funcionar desde o primeiro dia.
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
    icon: '📦',
    title: 'Controle de Estoque',
    description: 'Acompanhe entradas, saídas e níveis de estoque em tempo real. Evite rupturas e desperdícios com visibilidade total do seu inventário.',
    tag: 'estoque → em tempo real',
    highlight: true,
  },
  {
    icon: '💰',
    title: 'Controle Financeiro',
    description: 'Receitas, despesas e fluxo de caixa centralizados. Tenha o panorama financeiro do seu negócio sempre à mão, sem planilhas.',
  },
  {
    icon: '👥',
    title: 'Cadastro de Clientes',
    description: 'Histórico completo de cada cliente — compras, preferências e contatos — tudo organizado para um atendimento mais eficiente.',
  },
  {
    icon: '⭐',
    title: 'Fidelidade com o Cliente',
    description: 'Programa de fidelidade integrado ao cadastro. Recompense clientes frequentes e aumente o ticket médio de forma automática.',
    tag: 'fidelidade → ativo',
  },
  {
    icon: '🔔',
    title: 'Lembretes Automatizados',
    description: 'Notificações automáticas para clientes e equipe — cobranças, retornos, aniversários e muito mais. Menos esquecimento, mais resultado.',
  },
  {
    icon: '🤝',
    title: 'CRM Integrado',
    description: 'Gestão de relacionamento com o cliente dentro do próprio sistema. Sem ferramentas externas, sem complicação.',
  },
]
</script>
