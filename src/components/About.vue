<template>
  <section id="about" class="py-20 bg-gradient-to-b from-[#DFDBD9]/20 to-white">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-5xl font-bold text-gray-900 relative inline-block">
          Nossa História
          <span class="absolute bottom-0 left-1/2 transform -translate-x-1/2 w-24 h-1 bg-[#7A5847]"></span>
        </h2>
        <p class="text-lg text-gray-600 max-w-3xl mx-auto mt-8">Conheça a trajetória da família Machado na fotografia através das gerações.</p>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
        <div class="relative group">
          <div class="absolute -top-4 -left-4 w-32 h-32 bg-[#7A5847] opacity-10 rounded-lg transform transition-all duration-300 group-hover:scale-105"></div>
          <div class="absolute -bottom-4 -right-4 w-32 h-32 bg-[#7A5847] opacity-10 rounded-lg transform transition-all duration-300 group-hover:scale-105"></div>
          <img 
            src="https://images.unsplash.com/photo-1537633552985-df8429e8048b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80"
            alt="Fotógrafo em ação" 
            id="about-image"
            class="w-full rounded-lg shadow-2xl relative z-10 transform transition-all duration-500 group-hover:scale-[1.02]"
          >
        </div>
        
        <div class="space-y-6">
          <div class="border-l-4 border-[#7A5847] pl-6">
            <h3 class="text-2xl md:text-3xl font-bold text-gray-900 mb-2">Nossa Trajetória na Fotografia</h3>
            <p class="text-gray-600 italic">Três gerações de paixão pela arte de capturar momentos</p>
          </div>
          
          <div class="space-y-6 text-gray-600 leading-relaxed">
            <p>
              <span class="text-[#7A5847] font-semibold">Nossa trajetória na fotografia</span> é algo que sempre nos orgulhamos de contar... Passada de geração em geração, hoje somamos mais de 30 anos de experiências vividas de registros permanentes na terceira geração de fotógrafos.
            </p>
            <p>
              <span class="text-[#7A5847] font-semibold">Trabalhamos em família para famílias</span>, nossa família cuidando da sua! O ambiente familiar promove intimidade e aquela sensação de estar em casa. Casa é lugar de conforto, bem estar, e de ficar a vontade, e é assim que queremos que se sinta: em casa!
            </p>
            
            <div class="bg-[#DFDBD9]/20 p-6 rounded-lg my-8">
              <h4 class="text-xl font-bold text-gray-800 mb-4">Nossa História</h4>
              <p class="mb-4">
                Tudo começou com o Jr. Machado que desde foi adolescente, infuenciado pelo seu pai, médico, porém cineasta por paixão. Mas apenas no final dos anos 80 o mundo dos eventos começou se tornar realidade, quando ele passou a fotografar para uma grande empresa no paraná.
              </p>
              <p class="mb-4">
                Não muito tempo depois, no ano de 1990 veio a se casar e em 1991, passou a trabalhar independente e construir sua carreira solo. Sua esposa agregou grandemente a empresa, e com ela nasceu um novo ofício que estamos ansiosos para te contar como foi em uma reunião!
              </p>
              <p>
                Enfim, anos mais tarde com suas filhas já adultas, uma delas também muito influenciada pela família, herda o talento na fotografia e passa a dividir com pai a arte e técnicas nos eventos.
              </p>
            </div>
            
            <p>
              Se quiser conhecer melhor nossos currículos, formações e especializações, teremos maior prazer em apresentar nossos constantes investimentos em estudos e aperfeiçoamentos.
            </p>
          </div>
          
          <div class="grid grid-cols-2 md:grid-cols-3 gap-3 mt-10">
            <div class="bg-white p-6 rounded-lg shadow-lg text-center transform transition-all duration-300 hover:scale-105 hover:shadow-xl">
              <div class="text-[#7A5847] text-4xl font-bold mb-2">30+</div>
              <p class="text-gray-600 font-medium">Anos de Experiência</p>
            </div>
            <div class="bg-white p-6 rounded-lg shadow-lg text-center transform transition-all duration-300 hover:scale-105 hover:shadow-xl">
              <div class="text-[#7A5847] text-4xl font-bold mb-2">500+</div>
              <p class="text-gray-600 font-medium">Eventos Realizados</p>
            </div>
            <div class="bg-white p-6 rounded-lg shadow-lg text-center transform transition-all duration-300 hover:scale-105 hover:shadow-xl">
              <div class="text-[#7A5847] text-4xl font-bold mb-2">300+</div>
              <p class="text-gray-600 font-medium">Casamentos</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template> 

<style>
#about-image {
  height: 550px;
  object-fit: cover;
  object-position: center;
  border-radius: 10px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

@media (max-width: 768px) {
  #about-image {
    height: 400px;
  }
}
</style>