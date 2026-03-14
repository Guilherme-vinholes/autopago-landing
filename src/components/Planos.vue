<template>
  <section id="planos" class="py-24 px-6">
    <div class="max-w-4xl mx-auto">

      <div class="text-center mb-16">
        <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Planos</span>
        <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
          Preço justo, sem enrolação
        </h2>
        <p class="font-body text-brand-muted mt-4 max-w-xl mx-auto">
          Uma estrutura de planos clara, pensada para o crescimento do seu negócio.
        </p>
      </div>

      <div class="grid md:grid-cols-2 gap-6">

        <!-- Plano Starter -->
        <div class="p-8 rounded-2xl bg-brand-surface border-glow flex flex-col">
          <div class="mb-6">
            <span class="font-mono text-xs text-brand-muted uppercase tracking-widest">Starter</span>
            <div class="mt-3 flex items-end gap-2">
              <span class="font-display font-bold text-4xl text-brand-text">R$ 200</span>
              <span class="font-body text-brand-muted text-sm mb-1">/mês</span>
            </div>
            <p class="font-body text-brand-muted text-sm mt-2">Ideal para quem está começando e quer testar sem risco.</p>
          </div>

          <ul class="space-y-3 flex-1 mb-8">
            <li v-for="item in starterFeatures" :key="item" class="flex items-center gap-3 font-body text-sm text-brand-muted">
              <svg class="w-4 h-4 text-brand-green flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
              </svg>
              {{ item }}
            </li>
          </ul>

          <a
            :href="whatsappUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="block text-center font-body font-semibold text-sm px-6 py-3.5 rounded-xl border border-brand-green/30 text-brand-green hover:bg-brand-green/10 transition-all duration-200"
          >
            Começar agora
          </a>
        </div>

        <!-- Plano Pro (destaque) -->
        <div class="p-8 rounded-2xl bg-brand-green/5 border border-brand-green/30 glow-green flex flex-col relative overflow-hidden">
          <!-- Badge -->
          <div class="absolute top-4 right-4">
            <span class="font-mono text-xs text-brand-black bg-brand-green px-3 py-1 rounded-full font-bold">Mais popular</span>
          </div>

          <div class="mb-6">
            <span class="font-mono text-xs text-brand-green uppercase tracking-widest">Pro</span>
            <div class="mt-3 flex items-end gap-2">
              <span class="font-display font-bold text-4xl text-brand-text">Sob consulta</span>
            </div>
            <p class="font-body text-brand-muted text-sm mt-2">Para negócios que precisam de mais poder e personalização.</p>
          </div>

          <ul class="space-y-3 flex-1 mb-8">
            <li v-for="item in proFeatures" :key="item" class="flex items-center gap-3 font-body text-sm text-brand-text">
              <svg class="w-4 h-4 text-brand-green flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
              </svg>
              {{ item }}
            </li>
          </ul>

          <a
            :href="whatsappUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="block text-center font-body font-semibold text-sm px-6 py-3.5 rounded-xl bg-brand-green text-brand-black hover:bg-brand-green-mid transition-all duration-200 hover:scale-105"
          >
            Falar com a equipe
          </a>
        </div>

      </div>

      <!-- Garantia -->
      <div class="mt-10 text-center">
        <p class="font-body text-brand-muted text-sm">
          🔒 Sem contrato de fidelidade · Cancele quando quiser · Suporte incluso em todos os planos
        </p>
      </div>

    </div>
  </section>
</template>

<script setup>
const whatsappUrl = 'https://wa.me/5514999999999?text=Ol%C3%A1%2C%20quero%20saber%20mais%20sobre%20o%20Autopago!'

const starterFeatures = [
  'Acesso a todos os 6 módulos',
  'Até 500 registros/mês',
  'Suporte via WhatsApp',
  'Configuração assistida',
  'Atualizações incluídas',
]

const proFeatures = [
  'Tudo do Starter',
  'Registros ilimitados',
  'Módulos personalizados',
  'Integrações dedicadas',
  'Gerente de conta exclusivo',
  'SLA garantido',
]
</script>
