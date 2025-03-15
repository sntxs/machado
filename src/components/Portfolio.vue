<template>
  <section id="portfolio" class="py-16 bg-[#DFDBD9]/20">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900">Nosso Portfólio</h2>
        <div class="w-24 h-1 bg-[#7A5847] mx-auto mt-4 mb-6"></div>
        <p class="text-lg text-gray-600 max-w-3xl mx-auto">Conheça alguns dos nossos trabalhos mais recentes e deixe-se
          inspirar.</p>
      </div>

      <!-- Filtros de Portfólio -->
      <div class="flex flex-wrap justify-center mb-8">
        <button @click="activeFilter = 'todos'" :class="[
          'px-4 py-2 mx-2 mb-2 rounded-md transition-colors',
          activeFilter === 'todos'
            ? 'bg-[#7A5847] text-white'
            : 'bg-white text-gray-700 hover:bg-[#7A5847]/10'
        ]">
          Todos
        </button>
        <button @click="activeFilter = 'casamentos'" :class="[
          'px-4 py-2 mx-2 mb-2 rounded-md transition-colors',
          activeFilter === 'casamentos'
            ? 'bg-[#7A5847] text-white'
            : 'bg-white text-gray-700 hover:bg-[#7A5847]/10'
        ]">
          Casamentos
        </button>
        <button @click="activeFilter = '15anos'" :class="[
          'px-4 py-2 mx-2 mb-2 rounded-md transition-colors',
          activeFilter === '15anos'
            ? 'bg-[#7A5847] text-white'
            : 'bg-white text-gray-700 hover:bg-[#7A5847]/10'
        ]">
          15 Anos
        </button>
        <button @click="activeFilter = 'ensaios'" :class="[
          'px-4 py-2 mx-2 mb-2 rounded-md transition-colors',
          activeFilter === 'ensaios'
            ? 'bg-[#7A5847] text-white'
            : 'bg-white text-gray-700 hover:bg-[#7A5847]/10'
        ]">
          Ensaios
        </button>
        <button @click="activeFilter = 'eventos'" :class="[
          'px-4 py-2 mx-2 mb-2 rounded-md transition-colors',
          activeFilter === 'eventos'
            ? 'bg-[#7A5847] text-white'
            : 'bg-white text-gray-700 hover:bg-[#7A5847]/10'
        ]">
          Eventos
        </button>
      </div>

      <!-- Grid de Portfólio -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div v-for="(item, index) in filteredPortfolio" :key="index"
          class="group relative overflow-hidden rounded-lg shadow-md cursor-pointer h-[300px]" @click="openLightbox(item)">
          <div class="h-full w-full">
            <img :src="item.image" :alt="item.title"
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
          </div>
          <div
            class="absolute inset-0 bg-gradient-to-t from-[#7A5847]/90 via-black/30 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex flex-col justify-end p-6">
            <h3 class="text-white text-xl font-bold">{{ item.title }}</h3>
            <p class="text-[#DFDBD9] text-sm">{{ item.category }}</p>
          </div>
        </div>
      </div>

      <!-- Lightbox -->
      <div v-if="lightbox.open" class="fixed inset-0 z-50 flex items-center justify-center bg-black/90"
        @click="closeLightbox">
        <div class="relative max-w-4xl max-h-screen p-4" @click.stop>
          <button @click="closeLightbox" class="absolute top-4 right-4 text-white hover:text-blue-400 z-10">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24"
              stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
          <img :src="lightbox.image" :alt="lightbox.title" class="max-w-full max-h-[80vh] mx-auto">
          <div class="text-center mt-4">
            <h3 class="text-white text-xl font-bold">{{ lightbox.title }}</h3>
            <p class="text-gray-300">{{ lightbox.description }}</p>
          </div>
        </div>
      </div>

      <div class="text-center mt-12">
        <a href="#contact"
          class="inline-block bg-[#7A5847] hover:bg-[#8a6957] text-white font-medium py-3 px-8 rounded-md transition-colors">
          Vamos Trabalhar Juntos
        </a>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

// Estado do filtro ativo
const activeFilter = ref('todos');

// Estado do lightbox
const lightbox = ref({
  open: false,
  image: '',
  title: '',
  description: ''
});

// Dados do portfólio
const portfolio = [
  {
    image: 'https://images.unsplash.com/photo-1511285560929-80b456fea0bc?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Casamento Ana & Pedro',
    category: 'Casamentos',
    filter: 'casamentos',
    description: 'Um lindo casamento ao ar livre realizado em uma fazenda histórica.'
  },
  {
    image: 'https://images.unsplash.com/photo-1519741497674-611481863552?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Casamento Juliana & Marcos',
    category: 'Casamentos',
    filter: 'casamentos',
    description: 'Cerimônia intimista realizada ao pôr do sol na praia.'
  },
  {
    image: 'https://images.unsplash.com/photo-1502635385003-ee1e6a1a742d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Aniversário de 15 Anos - Maria',
    category: '15 Anos',
    filter: '15anos',
    description: 'Festa temática com decoração personalizada e ensaio fotográfico exclusivo.'
  },
  {
    image: 'https://images.unsplash.com/photo-1533738363-b7f9aef128ce?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Ensaio Pré-Wedding',
    category: 'Ensaios',
    filter: 'ensaios',
    description: 'Ensaio realizado no centro histórico da cidade.'
  },
  {
    image: 'https://images.unsplash.com/photo-1529636798458-92182e662485?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Aniversário de 15 Anos - Camila',
    category: '15 Anos',
    filter: '15anos',
    description: 'Celebração sofisticada com decoração em tons de rosa e dourado.'
  },
  {
    image: 'https://images.unsplash.com/photo-1519671482749-fd09be7ccebf?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Evento Corporativo',
    category: 'Eventos',
    filter: 'eventos',
    description: 'Cobertura completa de evento empresarial com mais de 200 convidados.'
  },
  {
    image: 'https://images.unsplash.com/photo-1522673607200-164d1b6ce486?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Ensaio Gestante',
    category: 'Ensaios',
    filter: 'ensaios',
    description: 'Ensaio fotográfico ao ar livre celebrando a maternidade.'
  },
  {
    image: 'https://images.unsplash.com/photo-1507504031003-b417219a0fde?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Casamento Noturno',
    category: 'Casamentos',
    filter: 'casamentos',
    description: 'Cerimônia realizada sob as estrelas com iluminação especial.'
  },
  {
    image: 'https://images.unsplash.com/photo-1472653431158-6364773b2a56?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
    title: 'Formatura Universitária',
    category: 'Eventos',
    filter: 'eventos',
    description: 'Cobertura completa de cerimônia de formatura e festa.'
  }
];

// Filtragem do portfólio
const filteredPortfolio = computed(() => {
  if (activeFilter.value === 'todos') {
    return portfolio;
  }
  return portfolio.filter(item => item.filter === activeFilter.value);
});

// Funções do lightbox
function openLightbox(item: any) {
  lightbox.value = {
    open: true,
    image: item.image,
    title: item.title,
    description: item.description
  };
  // Prevenir rolagem do body quando o lightbox está aberto
  document.body.style.overflow = 'hidden';
}

function closeLightbox() {
  lightbox.value.open = false;
  // Restaurar rolagem do body
  document.body.style.overflow = '';
}
</script>