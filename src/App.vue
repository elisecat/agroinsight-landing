<template>
  <div class="flex flex-col min-h-screen">
    <header class="p-0 shadow-lg">
      <div class="mx-auto">
        <Navbar :routes="[]" />
      </div>
    </header>

    <main :class="[$route.path !== '/inicio' ? 'container mx-auto flex-grow' : 'flex-grow']">
      <RouterView />
    </main>

    <footer class="mt-auto">
      <Footer />
    </footer>
  </div>
</template>

<script setup lang="ts">
import { RouterView, useRoute } from 'vue-router'
import Navbar from './components/shared/Navbar.vue'
import Footer from './components/shared/Footer.vue'

// const navRoutes = [
//   // { path: '/pentathlon', name: 'Pentathlon', icon: 'fas fa-trophy' },
//   { path: '/inicio', name: 'Inicio', icon: 'fas fa-home' },
//   { path: '/login', name: 'Inicia sesión', icon: 'fas fa-user' },
// ]

const $route = useRoute()
</script>
