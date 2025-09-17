<template>
  <div class="min-h-screen bg-white">
    <Navbar />
    <router-view />
    <Footer />
  </div>
</template>

<script setup lang="ts">
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
</script>

<style>
html {
  scroll-behavior: smooth;
}

/* Animação para o nome da empresa */
@keyframes logoReveal {
  0% {
    letter-spacing: -8px;
    opacity: 0;
    filter: blur(4px);
  }
  100% {
    letter-spacing: normal;
    opacity: 1;
    filter: blur(0);
  }
}

.text-[#7A5847], .text-[#DFDBD9] {
  animation: colorPulse 3s infinite alternate;
}

@keyframes colorPulse {
  0% {
    text-shadow: 0 0 5px rgba(122, 88, 71, 0.3);
  }
  100% {
    text-shadow: 0 0 15px rgba(122, 88, 71, 0.6);
  }
}

nav h1 {
  animation: logoReveal 1.5s ease-out forwards;
}

/* Cores personalizadas */
:root {
  --color-primary: #7A5847;
  --color-secondary: #DFDBD9;
}
</style>