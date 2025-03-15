<template>
  <section id="home" class="pt-24 pb-12 md:pt-32 md:pb-24 relative overflow-hidden">
    <!-- Background com efeito parallax -->
    <div class="absolute inset-0 bg-black">
      <img
        src="https://images.unsplash.com/photo-1537633552985-df8429e8048b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80"
        alt="Fotografia de casamento" class="w-full h-full object-cover opacity-60">
    </div>

    <!-- Elemento decorativo flutuante -->
    <div class="absolute top-1/4 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-10 opacity-10">
      <div
        class="text-white text-[150px] md:text-[250px] font-bold tracking-widest animate-float select-none pointer-events-none">
        M
      </div>
    </div>

    <div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="flex flex-col items-center text-center">
        <!-- Nome da empresa com destaque -->
        <div class="logo-container mb-2 animate-fade-in">
          <h1 class="text-5xl md:text-7xl font-bold text-white tracking-wider">
            <span class="text-[#DFDBD9]">MACHADO</span> <span class="text-[#7A5847]">FOTOGRAFIA</span> <span
              class="text-[#DFDBD9]">E</span> <span class="text-[#7A5847]">EVENTOS</span>
          </h1>
          <div class="logo-shadow"></div>
        </div>
        <div class="w-24 h-1 bg-[#7A5847] mx-auto mb-6 animate-fade-in-delay"></div>

        <h2 class="text-3xl md:text-5xl font-bold text-white mb-6 animate-fade-in-delay">
          Capturando <span class="text-[#DFDBD9]">Momentos</span> Inesquecíveis
        </h2>
        <p class="text-xl text-gray-200 mb-8 max-w-3xl animate-fade-in-delay-2">
          Transformamos seus momentos especiais em memórias eternas através da arte da fotografia e da excelência em
          eventos.
        </p>
        <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4 animate-fade-in-delay-3">
          <a @click.prevent="scrollToSection('portfolio')" href="javascript:void(0)"
            class="bg-[#7A5847] hover:bg-[#8a6957] text-white font-medium py-3 px-8 rounded-md transition-colors transform hover:scale-105 cursor-pointer inline-block text-center">
            Ver Portfólio
          </a>
          <a @click.prevent="scrollToSection('contact')" href="javascript:void(0)"
            class="border-2 border-[#DFDBD9] text-[#DFDBD9] hover:bg-[#DFDBD9]/10 font-medium py-3 px-8 rounded-md transition-colors transform hover:scale-105 cursor-pointer inline-block text-center">
            Agende uma Sessão
          </a>
        </div>
      </div>
    </div>

    <!-- Indicador de rolagem - visível apenas em telas maiores -->
    <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 animate-bounce z-10 hidden md:block">
      <a @click.prevent="scrollToSection('about')" href="javascript:void(0)" 
         class="text-white block cursor-pointer">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
        </svg>
      </a>
    </div>
  </section>
</template>

<script setup lang="ts">
// Função para rolar suavemente até a seção
function scrollToSection(sectionId: string) {
  const element = document.getElementById(sectionId);
  if (element) {
    // Rola até o elemento sem alterar a URL
    element.scrollIntoView({ behavior: 'smooth' });
  }
}
</script>

<style scoped>
.animate-fade-in {
  animation: fadeIn 1s ease-in-out;
}

.animate-fade-in-delay {
  animation: fadeIn 1s ease-in-out 0.3s;
  animation-fill-mode: both;
}

.animate-fade-in-delay-2 {
  animation: fadeIn 1s ease-in-out 0.6s;
  animation-fill-mode: both;
}

.animate-fade-in-delay-3 {
  animation: fadeIn 1s ease-in-out 0.9s;
  animation-fill-mode: both;
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.logo-container {
  position: relative;
  display: inline-block;
}

.logo-shadow {
  position: absolute;
  bottom: -10px;
  left: 0;
  right: 0;
  height: 5px;
  background: linear-gradient(90deg, transparent, #7A5847, #DFDBD9, #7A5847, transparent);
  border-radius: 50%;
  filter: blur(8px);
  opacity: 0.7;
  animation: glow 3s infinite alternate;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes float {
  0% {
    transform: translateY(0px) rotate(0deg);
  }

  50% {
    transform: translateY(-20px) rotate(5deg);
  }

  100% {
    transform: translateY(0px) rotate(0deg);
  }
}

@keyframes glow {
  0% {
    opacity: 0.5;
    width: 70%;
    margin-left: 15%;
  }

  100% {
    opacity: 0.8;
    width: 90%;
    margin-left: 5%;
  }
}
</style>