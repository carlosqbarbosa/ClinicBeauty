<template>
    <header class="relative overflow-hidden bg-gradient-to-r from-pink-100 to-purple-100" id="home">
        <article class="max-w-screen-x1 mx-auto px-4 sm:px-8 py-16 md:py-28 flex flex-col-reverse 
        lg:flex-row items-center gap-10 lg:gap-20">
        <!--Hero Content-->
        <section class="w-full lg:w-1/2 text-center lg:text-left">
          <hgroup data-aos="fade-up" data-aos-duration="500">
            <h1 class="text-3xl md:text-4xl lg:text-6xl font-bold text-gray-800 mb-4">
                Enhance Your Natural
                <mark class="text-pink-600 bg-transparent">Beauty</mark>
            </h1>
            <p class="text-base sm:text-lg text-gray-600 mb-8 max-w-xl mx-auto lg:mx-0">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                Nam laborum blanditiis tempore dolorem quam facilis porro impedit illo, velit quibusdam fuga, alias vero iste dolore tenetur fugit? 
                Maiores, quibusdam hic?
            </p>
          </hgroup> 
          <!--CTA buttons--> 
          <nav data-aos="fade-up" 
          data-aos-delay="600" 
            class="flex flex-col sm:flex-row justify-center lg:justify-start gap-4 mb-12">
                <a href="#appointment" 
                  class="bg-pink-600 hover:bg-pink-700 text-white text-center px-8 py-3 rounded-full 
                  transition shadow-lg">
                    Book a Consultation
                </a>
                <a href="#services"
                class="border border-pink-600 text-pink-600 hover:bg-pink-50
                text-center px-8 py-3 rounded-full transition" aria-label="Explore our Services">Explore Services</a>
            </nav>
            <!--Status Section-->
            <aside data-aos="fade-up" data-aos-delay="800" class="py-4" >
              <ul class="flex flex-wrap justify-center lg:justify-start gap-x-6 gap-y-4 text-center">
                <li v-for="(start, index) in stats" :key="index" class="w-1/2 sm:w-auto">
                  <strong class="text-2x1 font-bold text-pink-600">{{ stats.value }}</strong>
                  <small class="block text-sm text-gray-600">{{ stats.label }}</small>
                </li>
              </ul>
            </aside>
        </section>

        <!--Hero Image-->
        <figure data-aos="fade-up" data-aos-delay="700" class="w-full lg:w-1/2 flex justify-center relative">
          <div class="relative w-full max-w-xs sm:max-sm md:max-w-md">
            <span class="bg-pink-500 rounded-full w-64 h-64 sm:w-80 sm:h-80 absolute -top-10 -letf-10
            opacity-20" aria-hidden="true"></span>
            <span class="bg-purple-400 rounded-full w-48 h-48 sm:w-64 sm:h-64 absolute -bottom-10 -right-10
            opacity-20"></span>
           <img :src="imageSrc" alt="Woman smiling after cosmetic treatment" 
            class="relative z-10 rounded-full shadow-2x1 w-full object-cover" 
            width="400" height="400" loading="eager"/>
          </div>
        </figure>
        </article>

    </header>
  
</template>

<script setup>
import { ref } from 'vue';
import imageSrc from '@/assets/mulher-esteticista-na-clinica-consulta-cliente.jpg'
const stats = ref([
  {value: '2500+', label:'Happy Clients'},
  {value:'15+', label:'Specialists'},
  {value:'50+', label:'traetments'},
  {value:'10+', label:'Years'}
])

</script>
