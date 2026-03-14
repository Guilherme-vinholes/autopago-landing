<template>
  <footer class="bg-[#07090D] border-t border-white/10 px-6 pt-16 pb-8">
    <div class="max-w-5xl mx-auto">

      <!-- Top -->
      <div class="grid md:grid-cols-3 gap-12 pb-12 border-b border-white/10">

        <!-- Logo + tagline -->
        <div class="flex flex-col gap-4">
          <a href="#" class="flex items-center gap-2">
            <img src="/logo_ap2.png" alt="Autopago" class="h-10 w-auto" />
            <span class="font-display font-bold text-xl text-white">
              Auto<span style="color: #4ae8af">pago</span>
            </span>
          </a>
          <p class="font-body text-sm text-white/40 leading-relaxed max-w-xs">
            Tecnologia que gera retorno desde o primeiro cliente. Simples, direta e eficiente.
          </p>
          <div class="flex items-center gap-2 mt-1">
            <span class="w-2 h-2 rounded-full animate-pulse" style="background-color: #4ae8af"></span>
            <span class="font-mono text-xs text-white/40">status: ativo</span>
          </div>
        </div>

        <!-- Links -->
        <div class="flex flex-col gap-3">
          <span class="font-mono text-xs tracking-widest uppercase mb-1" style="color: #4ae8af">Navegação</span>
          <a href="#" class="font-body text-sm text-white/50 hover:text-white transition-colors">Início</a>
          <a href="#nos" class="font-body text-sm text-white/50 hover:text-white transition-colors">Quem somos</a>
          <a href="#autopago" class="font-body text-sm text-white/50 hover:text-white transition-colors">AutoPago</a>
          <a href="#contato" class="font-body text-sm text-white/50 hover:text-white transition-colors">Contate-nos</a>
        </div>

        <!-- Contato -->
        <div class="flex flex-col gap-3">
          <span class="font-mono text-xs tracking-widest uppercase mb-1" style="color: #4ae8af">Contato</span>
          <a
            :href="whatsappUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center gap-2 font-body text-sm text-white/50 hover:text-white transition-colors"
          >
            <svg class="w-4 h-4 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
              <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
            </svg>
            Falar no WhatsApp
          </a>
          <p class="font-body text-sm text-white/50">Bauru, SP — Brasil</p>
        </div>

      </div>

      <!-- Bottom -->
      <div class="pt-8 flex flex-col md:flex-row items-center justify-between gap-4">
        <p class="font-mono text-xs text-white/30">
          © 2026 Autopago · CNPJ 63.643.463/0001-91 · Onde custo vira resultado
        </p>
        <p class="font-mono text-xs text-white/20">
          Todos os direitos reservados
        </p>
      </div>

    </div>
  </footer>
</template>

<script setup>
const whatsappUrl = 'https://wa.me/5514999999999?text=Ol%C3%A1%2C%20quero%20saber%20mais%20sobre%20o%20Autopago!'
</script>
