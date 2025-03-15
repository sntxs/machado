<template>
  <section id="testimonials" class="py-16 bg-[#7A5847]/10">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900">Depoimentos</h2>
        <div class="w-24 h-1 bg-[#7A5847] mx-auto mt-4 mb-6"></div>
        <p class="text-lg text-gray-600 max-w-3xl mx-auto">O que nossos clientes dizem sobre nossos serviços.</p>
      </div>

      <div class="relative">
        <!-- Controles do Slider -->
        <div class="absolute top-1/2 -left-4 md:-left-8 transform -translate-y-1/2 z-10">
          <button 
            @click="prevSlide" 
            class="bg-white rounded-full p-2 shadow-md hover:bg-[#DFDBD9] transition-colors"
            aria-label="Slide anterior"
          >
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-[#7A5847]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
            </svg>
          </button>
        </div>
        
        <div class="absolute top-1/2 -right-4 md:-right-8 transform -translate-y-1/2 z-10">
          <button 
            @click="nextSlide" 
            class="bg-white rounded-full p-2 shadow-md hover:bg-[#DFDBD9] transition-colors"
            aria-label="Próximo slide"
          >
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-[#7A5847]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
            </svg>
          </button>
        </div>

        <!-- Slider de Depoimentos -->
        <div class="overflow-hidden">
          <div 
            class="flex transition-transform duration-500 ease-in-out"
            :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
          >
            <div 
              v-for="(testimonial, index) in testimonials" 
              :key="index" 
              class="w-full flex-shrink-0 px-4"
            >
              <div class="bg-white rounded-lg shadow-md p-8 md:p-10">
                <div class="flex flex-col md:flex-row items-center md:items-start mb-6">
                  <div class="w-20 h-20 md:w-24 md:h-24 rounded-full overflow-hidden mb-4 md:mb-0 md:mr-6 flex-shrink-0">
                    <img :src="testimonial.image" :alt="testimonial.name" class="w-full h-full object-cover">
                  </div>
                  <div>
                    <h3 class="text-xl font-bold text-gray-900">{{ testimonial.name }}</h3>
                    <p class="text-blue-600">{{ testimonial.event }}</p>
                    <div class="flex mt-2">
                      <svg v-for="star in 5" :key="star" class="w-5 h-5" :class="star <= testimonial.rating ? 'text-yellow-400' : 'text-gray-300'" fill="currentColor" viewBox="0 0 20 20">
                        <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                      </svg>
                    </div>
                  </div>
                </div>
                <div class="relative">
                  <svg class="absolute -top-4 -left-4 w-10 h-10 text-blue-100" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z" />
                  </svg>
                  <p class="text-gray-600 italic">{{ testimonial.text }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Indicadores de Slide -->
        <div class="flex justify-center mt-8">
          <button 
            v-for="(_, index) in testimonials" 
            :key="index"
            @click="goToSlide(index)"
            class="w-3 h-3 mx-1 rounded-full"
            :class="currentSlide === index ? 'bg-[#7A5847]' : 'bg-gray-300 hover:bg-[#7A5847]/50'"
            :aria-label="`Ir para o depoimento ${index + 1}`"
          ></button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

// Estado do slider
const currentSlide = ref(0);
const autoplayInterval = ref<number | null>(null);

// Dados dos depoimentos
const testimonials = [
  {
    name: 'Ana Silva',
    event: 'Casamento',
    image: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80',
    rating: 5,
    text: 'O trabalho da Machado Fotografia foi simplesmente incrível! Eles capturaram cada momento especial do nosso casamento com sensibilidade e profissionalismo. As fotos ficaram lindas e o álbum superou todas as nossas expectativas. Recomendo de olhos fechados!'
  },
  {
    name: 'Carlos Mendes',
    event: 'Aniversário de 15 anos da filha',
    image: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80',
    rating: 5,
    text: 'Contratamos a equipe para o aniversário de 15 anos da minha filha e foi a melhor escolha que poderíamos ter feito. Desde o ensaio fotográfico até a cobertura da festa, tudo foi perfeito. A organização e o profissionalismo da equipe fizeram toda a diferença.'
  },
  {
    name: 'Juliana Costa',
    event: 'Ensaio de Gestante',
    image: 'https://images.unsplash.com/photo-1489424731084-a5d8b219a5bb?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80',
    rating: 5,
    text: 'Fiz um ensaio de gestante e fiquei encantada com o resultado! O fotógrafo soube capturar a essência desse momento tão especial na minha vida. As fotos transmitem exatamente a emoção que eu estava sentindo. Trabalho impecável!'
  },
  {
    name: 'Ricardo e Fernanda',
    event: 'Casamento',
    image: 'https://images.unsplash.com/photo-1463453091185-61582044d556?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80',
    rating: 5,
    text: 'Nossa experiência com a Machado Fotografia foi excepcional! Desde o primeiro contato até a entrega das fotos, fomos tratados com muita atenção. As fotos do nosso casamento ficaram deslumbrantes e conseguiram capturar a essência da nossa celebração.'
  }
];

// Funções de controle do slider
function nextSlide() {
  currentSlide.value = (currentSlide.value + 1) % testimonials.length;
}

function prevSlide() {
  currentSlide.value = (currentSlide.value - 1 + testimonials.length) % testimonials.length;
}

function goToSlide(index: number) {
  currentSlide.value = index;
}

function startAutoplay() {
  autoplayInterval.value = window.setInterval(() => {
    nextSlide();
  }, 5000);
}

function stopAutoplay() {
  if (autoplayInterval.value !== null) {
    clearInterval(autoplayInterval.value);
    autoplayInterval.value = null;
  }
}

// Lifecycle hooks
onMounted(() => {
  startAutoplay();
});

onBeforeUnmount(() => {
  stopAutoplay();
});
</script> 