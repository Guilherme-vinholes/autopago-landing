<template>
  <section id="faq" class="py-24 px-6 bg-brand-surface/30">
    <div class="max-w-3xl mx-auto">

      <div class="text-center mb-16">
        <span class="font-mono text-xs text-brand-green tracking-widest uppercase">FAQ</span>
        <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
          Perguntas frequentes
        </h2>
      </div>

      <div class="space-y-3">
        <div
          v-for="(item, i) in faqs"
          :key="i"
          class="rounded-2xl bg-brand-surface border-glow overflow-hidden"
        >
          <button
            @click="toggle(i)"
            class="w-full flex items-center justify-between px-6 py-5 text-left hover:bg-white/5 transition-colors"
          >
            <span class="font-body font-medium text-brand-text text-sm md:text-base">{{ item.question }}</span>
            <svg
              :class="['w-4 h-4 text-brand-green flex-shrink-0 ml-4 transition-transform duration-200', open === i ? 'rotate-180' : '']"
              fill="none" stroke="currentColor" viewBox="0 0 24 24"
            >
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
            </svg>
          </button>
          <div v-if="open === i" class="px-6 pb-5">
            <p class="font-body text-brand-muted text-sm leading-relaxed">{{ item.answer }}</p>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const open = ref(null)

const toggle = (i) => {
  open.value = open.value === i ? null : i
}

const faqs = [
  {
    question: 'Como funciona o modelo de ROI imediato?',
    answer: 'Simples: nosso plano custa R$ 200/mês. Se você usa o Autopago para fechar um único cliente, esse valor já cobre a mensalidade inteira. Tudo o que vier depois é retorno líquido para o seu negócio.',
  },
  {
    question: 'Preciso de conhecimento técnico para usar?',
    answer: 'Não. O Autopago foi desenvolvido para ser intuitivo. Nossa equipe configura tudo junto com você no onboarding e oferece suporte contínuo via WhatsApp.',
  },
  {
    question: 'Posso cancelar a qualquer momento?',
    answer: 'Sim. Não trabalhamos com fidelidade ou multas. Se o sistema não fizer sentido para o seu negócio, você cancela quando quiser.',
  },
  {
    question: 'O que são os 6 módulos incluídos?',
    answer: 'Os módulos cobrem as principais necessidades de um negócio: gestão de clientes, financeiro, cobranças, automações, relatórios e comunicação. Cada módulo é ativado conforme sua necessidade.',
  },
  {
    question: 'O sistema funciona para qual tipo de empresa?',
    answer: 'O Autopago foi pensado para pequenas e médias empresas, MEIs e prestadores de serviço que precisam de tecnologia que realmente funcione — sem complexidade desnecessária.',
  },
]
</script>
