<template>
  <section id="about" class="py-16 bg-[#DFDBD9]/20">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900">Nossa História</h2>
        <div class="w-24 h-1 bg-[#7A5847] mx-auto mt-4 mb-6"></div>
        <p class="text-lg text-gray-600 max-w-3xl mx-auto">Conheça a paixão e dedicação por trás da Machado Fotografia e Eventos.</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
        <div class="relative">
          <div class="absolute -top-4 -left-4 w-24 h-24 bg-[#7A5847] opacity-20 rounded-lg"></div>
          <div class="absolute -bottom-4 -right-4 w-24 h-24 bg-[#7A5847] opacity-20 rounded-lg"></div>
          <img 
            src="https://images.unsplash.com/photo-1537633552985-df8429e8048b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80"
            alt="Fotógrafo em ação" 
            id="about-image"
            class="w-full rounded-lg shadow-xl relative z-10"
          >
        </div>
        
        <div>
          <h3 class="text-2xl font-bold text-gray-900 mb-4">Excelência em Fotografia e Eventos</h3>
          <p class="text-gray-600 mb-6">
            Fundada pelo fotógrafo João Machado, nossa empresa nasceu da paixão por capturar momentos únicos e transformá-los em memórias eternas. Com mais de 10 anos de experiência no mercado, nos especializamos em fotografia de casamentos, aniversários de 15 anos e eventos corporativos.
          </p>
          <p class="text-gray-600 mb-6">
            Nossa abordagem combina técnica profissional com sensibilidade artística, garantindo que cada momento seja registrado com autenticidade e emoção. Trabalhamos com uma equipe de profissionais talentosos e dedicados, comprometidos em oferecer um serviço personalizado e de alta qualidade.
          </p>
          
          <div class="grid grid-cols-2 gap-4 mt-8">
            <div class="bg-white p-4 rounded-lg shadow-md text-center">
              <div class="text-[#7A5847] text-3xl font-bold mb-2">10+</div>
              <p class="text-gray-600">Anos de Experiência</p>
            </div>
            <div class="bg-white p-4 rounded-lg shadow-md text-center">
              <div class="text-[#7A5847] text-3xl font-bold mb-2">500+</div>
              <p class="text-gray-600">Eventos Realizados</p>
            </div>
            <div class="bg-white p-4 rounded-lg shadow-md text-center">
              <div class="text-[#7A5847] text-3xl font-bold mb-2">300+</div>
              <p class="text-gray-600">Casamentos</p>
            </div>
            <div class="bg-white p-4 rounded-lg shadow-md text-center">
              <div class="text-[#7A5847] text-3xl font-bold mb-2">98%</div>
              <p class="text-gray-600">Clientes Satisfeitos</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template> 

<style>
#about-image {
  height: 500px;
  object-fit: cover;
  object-position: center;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
</style>