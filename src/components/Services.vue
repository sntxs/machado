<template>
  <section id="services" class="py-16 bg-white">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900">Nossos Serviços</h2>
        <div class="w-24 h-1 bg-[#7A5847] mx-auto mt-4 mb-6"></div>
        <p class="text-lg text-gray-600 max-w-3xl mx-auto">Oferecemos uma variedade de serviços fotográficos e de eventos para atender às suas necessidades.</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Serviço 1: Casamentos -->
        <div class="bg-[#DFDBD9]/10 rounded-lg overflow-hidden shadow-md transition-transform hover:scale-105">
          <div class="h-64 overflow-hidden">
            <img 
              src="https://images.unsplash.com/photo-1519741497674-611481863552?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" 
              alt="Fotografia de Casamento" 
              class="w-full h-full object-cover transition-transform hover:scale-110 duration-500"
            >
          </div>
          <div class="p-6">
            <h3 class="text-xl font-semibold text-gray-900 mb-2">Fotografia de Casamento</h3>
            <p class="text-gray-600 mb-4">Capturamos cada momento especial do seu grande dia, desde os preparativos até a festa, com sensibilidade e profissionalismo.</p>
            <ul class="text-gray-600 mb-4 space-y-1">
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Cobertura completa do evento
              </li>
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Ensaio pré-wedding
              </li>
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Álbum digital e impresso
              </li>
            </ul>
            <a href="#contact" class="inline-block bg-[#7A5847] hover:bg-[#8a6957] text-white font-medium py-2 px-4 rounded-md transition-colors">Solicitar Orçamento</a>
          </div>
        </div>

        <!-- Serviço 2: Aniversário de 15 anos -->
        <div class="bg-[#DFDBD9]/10 rounded-lg overflow-hidden shadow-md transition-transform hover:scale-105">
          <div class="h-64 overflow-hidden">
            <img 
              src="https://images.unsplash.com/photo-1502635385003-ee1e6a1a742d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" 
              alt="Aniversário de 15 anos" 
              class="w-full h-full object-cover transition-transform hover:scale-110 duration-500"
            >
          </div>
          <div class="p-6">
            <h3 class="text-xl font-semibold text-gray-900 mb-2">Aniversário de 15 Anos</h3>
            <p class="text-gray-600 mb-4">Transformamos o aniversário de 15 anos em uma experiência inesquecível, com fotografia e organização completa do evento.</p>
            <ul class="text-gray-600 mb-4 space-y-1">
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Ensaio fotográfico temático
              </li>
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Cobertura da festa
              </li>
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Cerimonial e assessoria
              </li>
            </ul>
            <a href="#contact" class="inline-block bg-[#7A5847] hover:bg-[#8a6957] text-white font-medium py-2 px-4 rounded-md transition-colors">Solicitar Orçamento</a>
          </div>
        </div>

        <!-- Serviço 3: Ensaios Fotográficos -->
        <div class="bg-[#DFDBD9]/10 rounded-lg overflow-hidden shadow-md transition-transform hover:scale-105">
          <div class="h-64 overflow-hidden">
            <img 
              src="https://images.unsplash.com/photo-1533738363-b7f9aef128ce?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" 
              alt="Ensaio Fotográfico" 
              class="w-full h-full object-cover transition-transform hover:scale-110 duration-500"
            >
          </div>
          <div class="p-6">
            <h3 class="text-xl font-semibold text-gray-900 mb-2">Ensaios Fotográficos</h3>
            <p class="text-gray-600 mb-4">Realizamos ensaios fotográficos personalizados para casais, famílias, gestantes e ensaios individuais.</p>
            <ul class="text-gray-600 mb-4 space-y-1">
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Locações diversas
              </li>
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Edição profissional
              </li>
              <li class="flex items-center">
                <svg class="w-4 h-4 text-[#7A5847] mr-2" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                </svg>
                Entrega rápida
              </li>
            </ul>
            <a href="#contact" class="inline-block bg-[#7A5847] hover:bg-[#8a6957] text-white font-medium py-2 px-4 rounded-md transition-colors">Solicitar Orçamento</a>
          </div>
        </div>
      </div>

      <div class="text-center mt-12">
        <a href="#contact" class="inline-block border border-[#7A5847] text-[#7A5847] hover:bg-[#7A5847]/10 font-medium py-3 px-8 rounded-md transition-colors">
          Consulte Todos os Nossos Serviços
        </a>
      </div>
    </div>
  </section>
</template> 