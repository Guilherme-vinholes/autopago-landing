<template>
  <section id="contato" class="py-24 px-6">
    <div class="max-w-2xl mx-auto">

      <div class="text-center mb-12">
        <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Contate-nos</span>
        <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
          Fale com a <span class="text-gradient">nossa equipe</span>
        </h2>
        <p class="font-body text-brand-muted mt-4 max-w-md mx-auto">
          Preencha o formulário e entraremos em contato para entender como o AutoPago pode ajudar o seu negócio.
        </p>
      </div>

      <!-- Form -->
      <form
        @submit.prevent="submit"
        class="bg-brand-surface border-glow rounded-2xl p-8 md:p-10 space-y-5"
      >
        <div class="grid sm:grid-cols-2 gap-5">
          <div>
            <label class="font-body text-sm text-brand-muted mb-1.5 block">Nome</label>
            <input
              v-model="form.name"
              type="text"
              placeholder="Seu nome"
              required
              class="w-full bg-brand-surface-2 border border-white/10 rounded-xl px-4 py-3 font-body text-sm text-brand-text placeholder-brand-muted/50 focus:outline-none focus:border-brand-green/50 transition-colors"
            />
          </div>
          <div>
            <label class="font-body text-sm text-brand-muted mb-1.5 block">Empresa</label>
            <input
              v-model="form.company"
              type="text"
              placeholder="Nome da empresa"
              class="w-full bg-brand-surface-2 border border-white/10 rounded-xl px-4 py-3 font-body text-sm text-brand-text placeholder-brand-muted/50 focus:outline-none focus:border-brand-green/50 transition-colors"
            />
          </div>
        </div>

        <div>
          <label class="font-body text-sm text-brand-muted mb-1.5 block">WhatsApp</label>
          <input
            v-model="form.phone"
            type="tel"
            placeholder="(00) 00000-0000"
            required
            class="w-full bg-brand-surface-2 border border-white/10 rounded-xl px-4 py-3 font-body text-sm text-brand-text placeholder-brand-muted/50 focus:outline-none focus:border-brand-green/50 transition-colors"
          />
        </div>

        <div>
          <label class="font-body text-sm text-brand-muted mb-1.5 block">Segmento do negócio</label>
          <select
            v-model="form.segment"
            class="w-full bg-brand-surface-2 border border-white/10 rounded-xl px-4 py-3 font-body text-sm text-brand-text focus:outline-none focus:border-brand-green/50 transition-colors appearance-none"
          >
            <option value="" disabled selected class="text-brand-muted">Selecione seu segmento</option>
            <option value="varejo">Varejo / Loja</option>
            <option value="servicos">Prestação de Serviços</option>
            <option value="alimentacao">Alimentação</option>
            <option value="saude">Saúde e Estética</option>
            <option value="educacao">Educação</option>
            <option value="outro">Outro</option>
          </select>
        </div>

        <div>
          <label class="font-body text-sm text-brand-muted mb-1.5 block">Mensagem <span class="text-brand-muted/50">(opcional)</span></label>
          <textarea
            v-model="form.message"
            rows="3"
            placeholder="Conte um pouco sobre o seu negócio..."
            class="w-full bg-brand-surface-2 border border-white/10 rounded-xl px-4 py-3 font-body text-sm text-brand-text placeholder-brand-muted/50 focus:outline-none focus:border-brand-green/50 transition-colors resize-none"
          ></textarea>
        </div>

        <button
          type="submit"
          class="w-full font-body font-semibold py-4 rounded-xl transition-all duration-300 hover:brightness-90 hover:scale-[1.02] text-base"
          style="background-color: #4ae8af; color: #07090D;"
        >
          {{ submitted ? 'Mensagem enviada!' : 'Quero conhecer o AutoPago' }}
        </button>

        <p v-if="submitted" class="text-center font-body text-sm text-brand-green">
          Recebemos seu contato. Nossa equipe vai falar com você em breve!
        </p>
      </form>

    </div>
  </section>
</template>

<script setup>
import { ref, reactive } from 'vue'

const submitted = ref(false)

const form = reactive({
  name: '',
  company: '',
  phone: '',
  segment: '',
  message: '',
})

const submit = () => {
  const text = encodeURIComponent(
    `Olá! Vim pela landing page.\n\n` +
    `*Nome:* ${form.name}\n` +
    `*Empresa:* ${form.company || 'Não informado'}\n` +
    `*WhatsApp:* ${form.phone}\n` +
    `*Segmento:* ${form.segment || 'Não informado'}\n` +
    `*Mensagem:* ${form.message || 'Nenhuma mensagem adicional'}`
  )
  submitted.value = true
  window.open(`https://wa.me/5514999999999?text=${text}`, '_blank')
}
</script>
