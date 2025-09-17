<template>
  <nav class="fixed top-0 left-0 right-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <div class="flex-shrink-0 flex items-center">
            <div class="img-machado mr-3">
              <img src="../assets/logo-machado.png" alt="Logo Machado Fotografia e Eventos" class="w-14 h-14">
            </div>
          </div>
        </div>
        <div class="hidden md:block">
          <div class="ml-10 flex items-baseline space-x-8">
            <a @click.prevent="goToAndScroll('#home')" href="/"
              class="text-gray-800 hover:text-[#7A5847] px-3 py-2 rounded-md text-sm font-medium transition-colors cursor-pointer">Início</a>
            <a @click.prevent="goToAndScroll('#about')" href="/"
              class="text-gray-800 hover:text-[#7A5847] px-3 py-2 rounded-md text-sm font-medium transition-colors cursor-pointer">Sobre</a>
            <a @click.prevent="goToAndScroll('#services')" href="/"
              class="text-gray-800 hover:text-[#7A5847] px-3 py-2 rounded-md text-sm font-medium transition-colors cursor-pointer">Serviços</a>
            <a @click.prevent="goToAndScroll('#portfolio')" href="/"
              class="text-gray-800 hover:text-[#7A5847] px-3 py-2 rounded-md text-sm font-medium transition-colors cursor-pointer">Portfólio</a>
            <a @click.prevent="goToAndScroll('#testimonials')" href="/"
              class="text-gray-800 hover:text-[#7A5847] px-3 py-2 rounded-md text-sm font-medium transition-colors cursor-pointer">Depoimentos</a>
            <a @click.prevent="goToAndScroll('#contact')" href="/"
              class="text-gray-800 hover:text-[#7A5847] px-3 py-2 rounded-md text-sm font-medium transition-colors cursor-pointer">Contato</a>
          </div>
        </div>
        <div class="md:hidden">
          <button @click="mobileMenuOpen = !mobileMenuOpen" class="text-gray-800 hover:text-[#7A5847]">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24"
              stroke="currentColor">
              <path v-if="!mobileMenuOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16" />
              <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Menu mobile -->
    <div v-if="mobileMenuOpen" class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3 bg-white border-b border-gray-100">
        <a @click.prevent="goToAndScroll('#home'); mobileMenuOpen = false" href="/"
          class="text-gray-800 hover:text-[#7A5847] block px-3 py-2 rounded-md text-base font-medium cursor-pointer">Início</a>
        <a @click.prevent="goToAndScroll('#about'); mobileMenuOpen = false" href="/"
          class="text-gray-800 hover:text-[#7A5847] block px-3 py-2 rounded-md text-base font-medium cursor-pointer">Sobre</a>
        <a @click.prevent="goToAndScroll('#services'); mobileMenuOpen = false" href="/"
          class="text-gray-800 hover:text-[#7A5847] block px-3 py-2 rounded-md text-base font-medium cursor-pointer">Serviços</a>
        <a @click.prevent="goToAndScroll('#portfolio'); mobileMenuOpen = false" href="/"
          class="text-gray-800 hover:text-[#7A5847] block px-3 py-2 rounded-md text-base font-medium cursor-pointer">Portfólio</a>
        <a @click.prevent="goToAndScroll('#testimonials'); mobileMenuOpen = false" href="/"
          class="text-gray-800 hover:text-[#7A5847] block px-3 py-2 rounded-md text-base font-medium cursor-pointer">Depoimentos</a>
        <a @click.prevent="goToAndScroll('#contact'); mobileMenuOpen = false" href="/"
          class="text-gray-800 hover:text-[#7A5847] block px-3 py-2 rounded-md text-base font-medium cursor-pointer">Contato</a>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, nextTick } from 'vue';
import { useRouter } from 'vue-router'

const mobileMenuOpen = ref(false);

const router = useRouter()

async function goToAndScroll(hash: string) {
  if (router.currentRoute.value.name !== 'home') {
    await router.push({ name: 'home' })
    await nextTick()
  }
  const id = hash.replace('#','')
  const el = document.getElementById(id)
  if (el) el.scrollIntoView({ behavior: 'smooth' })
}
</script>

<style scoped>
@keyframes revealText {
  0% {
    transform: translateY(100%);
    opacity: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;
  }
}
</style>