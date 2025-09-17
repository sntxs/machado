<template>
  <section id="portfolio" class="py-16 bg-[#DFDBD9]/20">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900">Nosso Portfólio</h2>
        <div class="w-24 h-1 bg-[#7A5847] mx-auto mt-4 mb-6"></div>
        <p class="text-lg text-gray-600 max-w-3xl mx-auto">Conheça alguns dos nossos trabalhos mais recentes e deixe-se
          inspirar.</p>
      </div>

      

      <!-- Grid de Portfólio (8 cards) -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div v-for="card in cards" :key="card.slug"
          class="group relative overflow-hidden rounded-lg shadow-md cursor-pointer h-[260px]"
          @click="goTo(card.slug)">
          <img :src="card.image" :alt="card.title"
               class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110" />
          <div class="absolute inset-0 bg-black/0 group-hover:bg-black/50 transition-colors duration-300"></div>
          <div class="absolute inset-x-0 bottom-0 p-4 translate-y-6 group-hover:translate-y-0 transition-transform duration-300">
            <div class="bg-[#7A5847]/90 text-white rounded-md px-3 py-2 inline-block">
              <p class="text-xs uppercase tracking-wide">{{ card.badge }}</p>
              <h3 class="text-lg font-semibold">{{ card.title }}</h3>
            </div>
          </div>
        </div>
      </div>

      

      <div class="text-center mt-12">
        <a @click.prevent="scrollToSection('contact')" href="javascript:void(0)" 
           class="inline-block bg-[#7A5847] hover:bg-[#8a6957] text-white font-medium py-3 px-8 rounded-md transition-colors cursor-pointer">
          Vamos Trabalhar Juntos
        </a>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()

const cards = [
  // 2 Casamentos
  {
    slug: 'casamento-ana-pedro',
    badge: 'Casamento',
    title: 'Ana & Pedro',
    image: 'https://images.unsplash.com/photo-1511285560929-80b456fea0bc?auto=format&fit=crop&w=1350&q=80'
  },
  {
    slug: 'casamento-juliana-marcos',
    badge: 'Casamento',
    title: 'Juliana & Marcos',
    image: 'https://images.unsplash.com/photo-1507504031003-b417219a0fde?auto=format&fit=crop&w=1350&q=80'
  },
  // 2 Debutantes
  {
    slug: 'debutante-maria',
    badge: '15 Anos',
    title: 'Maria',
    image: 'https://images.unsplash.com/photo-1502635385003-ee1e6a1a742d?auto=format&fit=crop&w=1350&q=80'
  },
  {
    slug: 'debutante-camila',
    badge: '15 Anos',
    title: 'Camila',
    image: 'https://images.unsplash.com/photo-1529636798458-92182e662485?auto=format&fit=crop&w=1350&q=80'
  },
  // 2 Ensaios
  {
    slug: 'ensaio-pre-wedding',
    badge: 'Ensaio',
    title: 'Pré-wedding',
    image: 'https://images.unsplash.com/photo-1533738363-b7f9aef128ce?auto=format&fit=crop&w=1350&q=80'
  },
  {
    slug: 'ensaio-urbano',
    badge: 'Ensaio',
    title: 'Urbano',
    image: 'https://images.unsplash.com/photo-1519671482749-fd09be7ccebf?auto=format&fit=crop&w=1350&q=80'
  },
  // 2 Gestante
  {
    slug: 'gestante-parque',
    badge: 'Gestante',
    title: 'No Parque',
    image: 'https://images.unsplash.com/photo-1522673607200-164d1b6ce486?auto=format&fit=crop&w=1350&q=80'
  },
  {
    slug: 'gestante-praia',
    badge: 'Gestante',
    title: 'Na Praia',
    image: 'https://images.unsplash.com/photo-1522673607200-164d1b6ce486?auto=format&fit=crop&w=1350&q=80'
  }
]

function goTo(slug: string) {
  router.push({ name: 'gallery', params: { slug } })
}

function scrollToSection(sectionId: string) {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>