# Autopago — Landing Page

Landing page oficial da Autopago. Vue 3 + TailwindCSS + Vite.

## Stack
- **Vue 3** com Composition API
- **TailwindCSS v3**
- **Vite** (bundler)

## Rodando localmente

```bash
npm install
npm run dev
```

## Build para produção

```bash
npm run build
```

Os arquivos finais ficam na pasta `/dist` — é essa pasta que sobe para o Azure.

## Azure Static Web Apps

Configurações de build:
- **App location:** `/`
- **Output location:** `dist`
- **Build command:** `npm run build`

## Personalizar

- **WhatsApp:** Busque `wa.me/5514999999999` nos componentes e substitua pelo número real
- **Cores:** `tailwind.config.js` → `theme.extend.colors.brand`
- **Fontes:** `tailwind.config.js` → `theme.extend.fontFamily`
- **Textos:** Cada seção é um componente separado em `src/components/`

## Estrutura

```
src/
  components/
    NavBar.vue        — Navbar fixa com scroll detection
    HeroSection.vue   — Hero principal com CTAs
    ComoFunciona.vue  — 3 passos do processo
    Beneficios.vue    — Grid de benefícios
    Planos.vue        — Tabela de planos
    FAQ.vue           — Accordion de perguntas
    CTAFooter.vue     — CTA final + rodapé
  App.vue
  main.js
  style.css
```
