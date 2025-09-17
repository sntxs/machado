<template>
  <section class="pt-24 pb-16 bg-[#DFDBD9]/20 min-h-screen">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="mb-8">
        <button @click="goBack" class="text-[#7A5847] hover:underline">← Voltar</button>
      </div>
      <div class="text-center mb-8">
        <h1 class="text-3xl md:text-4xl font-bold text-gray-900">{{ galleryTitle }}</h1>
        <p class="text-gray-600 mt-2">{{ gallerySubtitle }}</p>
      </div>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
        <div v-for="(img, idx) in images" :key="idx" class="aspect-[4/3] overflow-hidden rounded-lg shadow">
          <img :src="img" :alt="`${galleryTitle} – foto ${idx+1}`" class="w-full h-full object-cover" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { useRoute, useRouter } from 'vue-router'

type GalleryConfig = {
  title: string
  subtitle: string
  images: string[]
}

const router = useRouter()
const route = useRoute()

const galleries: Record<string, GalleryConfig> = {
  'casamento-ana-pedro': {
    title: 'Casamento – Ana & Pedro',
    subtitle: 'Celebração ao ar livre em fazenda histórica',
    images: Array.from({ length: 12 }).map((_, i) =>
      `https://images.unsplash.com/photo-1511285560929-80b456fea0bc?auto=format&fit=crop&w=1200&q=80&ixid=${i}`
    )
  },
  'casamento-juliana-marcos': {
    title: 'Casamento – Juliana & Marcos',
    subtitle: 'Pôr do sol na praia',
    images: Array.from({ length: 12 }).map((_, i) =>
      `https://images.unsplash.com/photo-1507504031003-b417219a0fde?auto=format&fit=crop&w=1200&q=80&ixid=${i}`
    )
  },
  'debutante-maria': {
    title: '15 Anos – Maria',
    subtitle: 'Festa temática com ensaio exclusivo',
    images: Array.from({ length: 12 }).map((_, i) =>
      `https://images.unsplash.com/photo-1502635385003-ee1e6a1a742d?auto=format&fit=crop&w=1200&q=80&ixid=${i}`
    )
  },
  'debutante-camila': {
    title: '15 Anos – Camila',
    subtitle: 'Celebração sofisticada',
    images: Array.from({ length: 12 }).map((_, i) =>
      `https://images.unsplash.com/photo-1529636798458-92182e662485?auto=format&fit=crop&w=1200&q=80&ixid=${i}`
    )
  },
  'ensaio-pre-wedding': {
    title: 'Ensaio – Pré-wedding',
    subtitle: 'Centro histórico da cidade',
    images: Array.from({ length: 12 }).map((_, i) =>
      `https://images.unsplash.com/photo-1533738363-b7f9aef128ce?auto=format&fit=crop&w=1200&q=80&ixid=${i}`
    )
  },
  'ensaio-urbano': {
    title: 'Ensaio – Urbano',
    subtitle: 'Cenas de rua e arquitetura',
    images: Array.from({ length: 12 }).map((_, i) =>
      `https://images.unsplash.com/photo-1519671482749-fd09be7ccebf?auto=format&fit=crop&w=1200&q=80&ixid=${i}`
    )
  },
  'gestante-parque': {
    title: 'Gestante – No Parque',
    subtitle: 'Luz natural e afeto',
    images: Array.from({ length: 12 }).map((_, i) =>
      `https://images.unsplash.com/photo-1522673607200-164d1b6ce486?auto=format&fit=crop&w=1200&q=80&ixid=${i}`
    )
  },
  'gestante-praia': {
    title: 'Gestante – Na Praia',
    subtitle: 'Brisa do mar ao entardecer',
    images: Array.from({ length: 12 }).map((_, i) =>
      `https://images.unsplash.com/photo-1522673607200-164d1b6ce486?auto=format&fit=crop&w=1200&q=80&ixid=${i}`
    )
  }
}

const slug = computed(() => String(route.params.slug || ''))

const gallery = computed<GalleryConfig>(() => {
  return galleries[slug.value] || {
    title: 'Galeria não encontrada',
    subtitle: 'Verifique o endereço e tente novamente',
    images: []
  }
})

const galleryTitle = computed(() => gallery.value.title)
const gallerySubtitle = computed(() => gallery.value.subtitle)
const images = computed(() => gallery.value.images)

function goBack() {
  router.back()
}
</script>


