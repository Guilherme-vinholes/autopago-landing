<template>
  <section id="nos" class="py-24 px-6 bg-brand-surface/30">
    <div class="max-w-5xl mx-auto">

      <div class="text-center mb-16">
        <span class="font-mono text-xs text-brand-green tracking-widest uppercase">Quem somos</span>
        <h2 class="font-display font-bold text-4xl md:text-5xl text-brand-text mt-3">
          Quem transforma <span class="text-gradient">tecnologia em resultado</span>
        </h2>
        <p class="font-body text-brand-muted mt-4 max-w-xl mx-auto">
          Um time pequeno, focado e comprometido em entregar tecnologia que realmente funciona para o seu negócio.
        </p>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <div
          v-for="(member, i) in team"
          :key="i"
          class="group flex flex-col items-center text-center p-8 rounded-2xl bg-brand-surface border-glow hover:border-brand-green/30 transition-all duration-300 hover:-translate-y-1"
        >
          <!-- Foto -->
          <div class="w-28 h-28 rounded-full overflow-hidden mb-5 border-2 border-brand-green/20 group-hover:border-brand-green/50 transition-colors duration-300 bg-brand-surface-2 flex items-center justify-center">
            <img
              v-if="member.photo"
              :src="member.photo"
              :alt="member.name"
              class="w-full h-full object-cover"
            />
            <span v-else class="font-display font-bold text-3xl text-brand-green/40">{{ member.initials }}</span>
          </div>

          <!-- Nome e cargo -->
          <h3 class="font-display font-bold text-xl text-brand-text mb-1">{{ member.name }}</h3>
          <span class="font-mono text-xs text-brand-green tracking-wider uppercase mb-4">{{ member.role }}</span>

          <!-- Bio -->
          <p class="font-body text-brand-muted text-sm leading-relaxed">{{ member.bio }}</p>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const team = [
  {
    name: 'Leonardo Wolber',
    initials: 'LW',
    role: 'Cargo / Função',
    bio: 'Breve apresentação sobre essa pessoa — o que faz, sua experiência e o que traz para o time da Autopago.',
    photo: '',
  },
  {
    name: 'Euclides Marques',
    initials: 'EM',
    role: 'Cargo / Função',
    bio: 'Breve apresentação sobre essa pessoa — o que faz, sua experiência e o que traz para o time da Autopago.',
    photo: '',
  },
  {
    name: 'Guilherme Vinholes',
    initials: 'GV',
    role: 'Cargo / Função',
    bio: 'Breve apresentação sobre essa pessoa — o que faz, sua experiência e o que traz para o time da Autopago.',
    photo: '',
  },
]
</script>
