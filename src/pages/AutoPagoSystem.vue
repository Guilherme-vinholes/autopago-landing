<template>
  <div>
    <!-- Hero -->
    <section class="relative min-h-[70vh] flex items-center justify-center overflow-hidden pt-20 bg-[#07090D]">
      <div class="absolute inset-0 bg-grid opacity-30"></div>
      <div class="relative z-10 max-w-5xl mx-auto px-6 text-center">

        <div
          class="inline-flex items-center gap-2 bg-white/10 backdrop-blur-sm border border-white/20 rounded-full px-3 py-1.5 mb-6 opacity-0 animate-fade-up"
          style="animation-fill-mode: forwards;"
        >
          <span class="w-2 h-2 rounded-full bg-brand-green animate-pulse flex-shrink-0"></span>
          <span class="font-mono text-xs text-white/70 tracking-wider uppercase">AutoPago System</span>
        </div>

        <h1
          class="font-display font-bold text-3xl sm:text-4xl md:text-5xl leading-tight tracking-tight mb-6 opacity-0 animate-fade-up delay-100 text-white"
          style="animation-fill-mode: forwards; font-style: normal;"
        >
          O sistema que <span class="text-gradient">se paga sozinho</span>
        </h1>

        <p
          class="font-body text-base md:text-xl text-white/70 max-w-2xl mx-auto mb-8 leading-relaxed opacity-0 animate-fade-up delay-200"
          style="animation-fill-mode: forwards;"
        >
          Conheça em detalhes cada módulo do AutoPago — uma plataforma completa de gestão pensada para pequenos e médios negócios.
        </p>

        <a
          href="#modulos"
          class="inline-flex items-center gap-2 text-white/60 hover:text-white font-body text-sm px-6 py-3 rounded-2xl border border-white/20 hover:border-white/40 transition-all duration-200 opacity-0 animate-fade-up delay-300"
          style="animation-fill-mode: forwards;"
        >
          Explorar módulos
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
          </svg>
        </a>
      </div>
    </section>

    <!-- Módulos -->
    <section id="modulos" class="py-24 px-6">
      <div class="max-w-5xl mx-auto">

        <div class="text-center mb-16">
          <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Módulos</span>
          <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
            Tudo o que você <span class="text-gradient">precisa</span>
          </h2>
          <p class="font-body text-brand-muted mt-4 max-w-xl mx-auto">
            Cada módulo foi pensado para resolver um problema real do seu dia a dia.
          </p>
        </div>

        <div class="grid md:grid-cols-2 gap-8">
          <div
            v-for="(mod, i) in modules"
            :key="i"
            class="group p-8 rounded-2xl bg-brand-surface border-glow hover:border-brand-green/30 transition-all duration-300 hover:-translate-y-1"
          >
            <div class="w-14 h-14 rounded-xl bg-brand-green/10 flex items-center justify-center mb-5 group-hover:bg-brand-green/20 transition-colors">
              <span class="text-2xl">{{ mod.icon }}</span>
            </div>
            <h3 class="font-display font-bold text-xl text-brand-text mb-3">{{ mod.title }}</h3>
            <p class="font-body text-brand-muted text-sm leading-relaxed mb-4">{{ mod.description }}</p>
            <ul class="space-y-2">
              <li
                v-for="(feat, j) in mod.features"
                :key="j"
                class="flex items-start gap-2 text-sm font-body text-brand-muted"
              >
                <span class="text-brand-green mt-0.5">✓</span>
                <span>{{ feat }}</span>
              </li>
            </ul>
          </div>
        </div>

      </div>
    </section>

    <!-- Diferenciais -->
    <section class="py-24 px-6 bg-brand-surface/30">
      <div class="max-w-5xl mx-auto">

        <div class="text-center mb-16">
          <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Diferenciais</span>
          <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
            Por que o <span class="text-gradient">AutoPago?</span>
          </h2>
        </div>

        <div class="grid md:grid-cols-3 gap-6">
          <div
            v-for="(diff, i) in differentials"
            :key="i"
            class="text-center p-8 rounded-2xl bg-brand-surface border-glow hover:border-brand-green/30 transition-all duration-300"
          >
            <div class="text-4xl mb-4">{{ diff.icon }}</div>
            <h3 class="font-display font-bold text-lg text-brand-text mb-2">{{ diff.title }}</h3>
            <p class="font-body text-brand-muted text-sm leading-relaxed">{{ diff.description }}</p>
          </div>
        </div>

      </div>
    </section>

    <!-- CTA -->
    <section class="py-24 px-6">
      <div class="max-w-3xl mx-auto text-center">
        <h2 class="font-display font-bold text-3xl md:text-4xl text-brand-text mb-4">
          Pronto para <span class="text-gradient">começar?</span>
        </h2>
        <p class="font-body text-brand-muted mb-8">
          Fale com um especialista e descubra como o AutoPago pode transformar a gestão do seu negócio.
        </p>
        <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
          <a
            href="https://wa.me/5514991373142?text=Ol%C3%A1%2C%20quero%20saber%20mais%20sobre%20o%20Autopago!"
            target="_blank"
            rel="noopener noreferrer"
            class="font-body font-semibold px-8 py-4 rounded-2xl transition-all duration-300 hover:scale-105 hover:brightness-90 text-base"
            style="background-color: #4ae8af; color: #07090D;"
          >
            Fale com especialista
          </a>
          <button
            @click="$emit('navigate', 'home')"
            class="flex items-center gap-2 text-brand-muted hover:text-brand-text font-body text-sm px-6 py-4 rounded-2xl border border-brand-green/20 hover:border-brand-green/40 transition-all duration-200"
          >
            ← Voltar para o início
          </button>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
defineEmits(['navigate'])

const modules = [
  {
    icon: '📦',
    title: 'Controle de Estoque',
    description: 'Gerencie todo o seu inventário com precisão e em tempo real.',
    features: [
      'Entradas e saídas automáticas',
      'Alertas de estoque baixo',
      'Relatórios por período',
      'Categorização de produtos',
    ],
  },
  {
    icon: '💰',
    title: 'Controle Financeiro',
    description: 'Tenha visão completa das finanças do seu negócio sem planilhas.',
    features: [
      'Fluxo de caixa em tempo real',
      'Contas a pagar e receber',
      'Relatórios financeiros',
      'Integração com estoque',
    ],
  },
  {
    icon: '👥',
    title: 'Cadastro de Clientes',
    description: 'Organize todos os dados dos seus clientes em um só lugar.',
    features: [
      'Histórico de compras',
      'Dados de contato centralizados',
      'Segmentação de clientes',
      'Busca rápida e filtros',
    ],
  },
  {
    icon: '⭐',
    title: 'Programa de Fidelidade',
    description: 'Fidelize seus clientes e aumente o ticket médio automaticamente.',
    features: [
      'Pontuação automática',
      'Recompensas personalizáveis',
      'Relatório de engajamento',
      'Integrado ao cadastro',
    ],
  },
  {
    icon: '🔔',
    title: 'Lembretes Automatizados',
    description: 'Nunca mais esqueça de cobrar, avisar ou acompanhar um cliente.',
    features: [
      'Notificações automáticas',
      'Cobranças programadas',
      'Lembretes de aniversário',
      'Alertas personalizáveis',
    ],
  },
  {
    icon: '🤝',
    title: 'CRM Integrado',
    description: 'Gestão de relacionamento completa dentro do próprio sistema.',
    features: [
      'Pipeline de vendas',
      'Histórico de interações',
      'Acompanhamento de leads',
      'Sem ferramentas externas',
    ],
  },
]

const differentials = [
  {
    icon: '⚡',
    title: 'Simples de usar',
    description: 'Interface intuitiva que qualquer pessoa da equipe aprende em minutos.',
  },
  {
    icon: '🔒',
    title: 'Seguro e confiável',
    description: 'Seus dados protegidos com criptografia e backups automáticos.',
  },
  {
    icon: '📱',
    title: 'Acesse de qualquer lugar',
    description: 'Sistema 100% online — funciona no computador, tablet e celular.',
  },
]
</script>
