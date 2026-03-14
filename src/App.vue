<template>
  <div class="min-h-screen bg-brand-black text-brand-text">
    <NavBar :current-page="currentPage" @navigate="goTo" />
    <main>
      <HomePage v-if="currentPage === 'home'" @navigate="goTo" />
      <AutoPagoSystem v-else-if="currentPage === 'system'" @navigate="goTo" />
    </main>
  </div>
</template>

<script setup>
import { ref, onMounted, nextTick } from 'vue'
import NavBar from './components/NavBar.vue'
import HomePage from './pages/HomePage.vue'
import AutoPagoSystem from './pages/AutoPagoSystem.vue'

const currentPage = ref('home')

// Detect initial route
const detectRoute = () => {
  const path = window.location.pathname.toLowerCase()
  if (path === '/nossosistema') {
    currentPage.value = 'system'
  } else {
    currentPage.value = 'home'
  }
}

const goTo = async (page, hash) => {
  currentPage.value = page

  if (page === 'system') {
    history.pushState({page: 'system'}, '', '/NossoSistema')
    window.scrollTo({ top: 0, behavior: 'smooth' })
  } else {
    history.pushState({page: 'home'}, '', '/')
    if (hash) {
      await nextTick()
      setTimeout(() => {
        const el = document.querySelector(hash)
        if (el) el.scrollIntoView({ behavior: 'smooth' })
      }, 100)
    } else {
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  }
}

// Handle browser back/forward
window.addEventListener('popstate', (e) => {
  if (e.state && e.state.page) {
    currentPage.value = e.state.page
  } else {
    detectRoute()
  }
  window.scrollTo({ top: 0, behavior: 'smooth' })
})

onMounted(() => {
  detectRoute()
  history.replaceState({page: currentPage.value}, '', window.location.pathname)
})
</script>
