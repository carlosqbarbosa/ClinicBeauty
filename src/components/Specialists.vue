<template>
  <section class="py-20 overflow-hidden bg-gradient-to-r from-blue-100 to-green-100" id="specialists">
    <div class="container mx-auto px-4">
      <!-- Section Header -->
      <header data-aos="fade-up" data-aos-delay="500" class="text-center mb-16">
        <h2 id="specialists-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
          Conheça nossos <span class="text-blue-600">Especialistas</span>
        </h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Nossa equipe de especialistas é dedicada a oferecer o mais alto padrão de cuidado e tratamentos personalizados para você.
        </p>
      </header>

      <!-- Specialists Grid -->
      <ul
        data-aos="fade-up"
        data-aos-delay="500"
        class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16"
        role="list"
      >
        <li
          v-for="doctor in specialists"
          :key="doctor.id"
          class="group relative"
          role="listitem"
        >
          <article
            class="flex flex-col rounded-xl shadow-lg overflow-hidden hover:shadow-xl transition-all duration-300 h-full bg-white"
          >
            <!-- Imagem -->
            <figure class="relative h-[260px] overflow-hidden">
              <img
                :src="doctor.image"
                :alt="doctor.name"
                class="w-full h-full object-cover object-top transition-transform duration-500 group-hover:scale-105"
                loading="lazy"
              />
              <span
                class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent"
                aria-hidden="true"
              ></span>

              <!-- Avaliação -->
              <aside
                class="absolute top-4 right-4 bg-white/90 px-3 py-1 rounded-full flex items-center shadow-sm"
                :aria-label="`Avaliação: ${doctor.rating} estrelas`"
              >
                <Icon
                  v-for="i in 5"
                  :key="i"
                  :icon="i <= doctor.rating ? 'mdi:star' : 'mdi:star-outline'"
                  class="text-yellow-400 inline"
                />
                <span class="ml-1 text-sm font-medium">{{ doctor.rating }}.0</span>
              </aside>
            </figure>

            <!-- Conteúdo -->
            <div class="flex flex-col justify-between flex-1 p-6 bg-blue-50">
              <header>
                <h3 class="text-xl font-bold text-gray-800 mb-1">
                  {{ doctor.name }}
                </h3>
                <p class="text-blue-600 font-medium mb-3">{{ doctor.role }}</p>
              </header>

              <p class="text-gray-600 mb-4 flex-1">{{ doctor.bio }}</p>

              <ul class="flex flex-wrap gap-2">
                <li v-for="(spec, i) in doctor.specialities" :key="i">
                  <span
                    class="bg-white text-blue-600 text-xs font-medium px-3 py-1 rounded-full shadow-sm"
                  >
                    {{ spec }}
                  </span>
                </li>
              </ul>
            </div>
          </article>
        </li>
      </ul>


      <!-- CTA Section -->
      <aside class="bg-gradient-to-r from-blue-100 to-green-100 rounded-2xl p-8 md:p-12 text-center relative overflow-hidden" data-aos="fade-up" data-aos-delay="500">
        <span class="absolute -top-20 -left-20 w-40 h-40 rounded-full bg-blue-200 opacity-20" aria-hidden="true"></span>
        <span class="absolute -bottom-20 -right-20 w-60 h-60 rounded-full bg-green-200 opacity-20" aria-hidden="true"></span>
        <div class="relative z-10">
          <h3 class="text-2xl md:text-3xl font-bold text-gray-800 mb-6">
            Pronto para Consultar Nossos Especialistas?
          </h3>
          <p class="text-lg text-gray-600 mb-8 max-w-2xl mx-auto">
            Agende uma consulta personalizada para conversar sobre seus objetivos estéticos e as opções de tratamento disponíveis.
          </p>
          <nav class="flex flex-col sm:flex-row justify-center gap-4">
            <a
              href="#appointment"
              class="bg-blue-600 hover:bg-blue-700 text-white text-center px-6 py-3 rounded-full inline-block transition shadow-md focus:outline-none focus:ring-2 focus:ring-blue-800 focus:ring-offset-2"
            >
              Agendar Consulta
            </a>
            <a
              href="#contact"
              class="border border-blue-600 text-blue-600 hover:bg-blue-50 px-8 py-3 rounded-full transition focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2"
              aria-label="Entre em contato"
            >
              Entre em contato
            </a>
          </nav>
        </div>
      </aside>
    </div>
  </section>
</template>

<script setup>
import Image1 from '@/assets/SpecialistsImg.jpg';
import Image2 from '@/assets/SpecialistsImg2.jpg';
import Image3 from '@/assets/SpecialistsImg4.jpg';
import { ref } from 'vue';
import { Icon } from '@iconify/vue';

const specialists = ref([
  {
    id: 1,
    name: 'Dra. Jane Alvez',
    role: 'Dermatologia Estética',
    image: Image1,
    bio: 'Especialista em tratamentos faciais, peelings e rejuvenescimento. Focada em resultados naturais e no bem-estar dos pacientes.',
    specialities: ['Peelings', 'Limpeza de Pele', 'Rejuvenescimento Facial'],
    rating: 5
  },
  {
    id: 2,
    name: 'Dr. Michael Borges',
    role: 'Harmonização Facial',
    image: Image2,
    bio: 'Apaixonado por realçar a beleza natural de cada paciente por meio de técnicas modernas de preenchimento e toxina botulínica.',
    specialities: ['Preenchimentos Faciais', 'Toxina Botulínica', 'Contorno Facial'],
    rating: 5
  },
  {
    id: 3,
    name: 'Dra. Emily Braga',
    role: 'Estética e Cosmetologia',
    image: Image3,
    bio: 'Realiza limpeza de pele, drenagem linfática e tratamentos corporais com foco em resultados e relaxamento.',
    specialities: ['Limpeza de Pele', 'Drenagem Linfática', 'Tratamentos Corporais'],
    rating: 5
  }
]);
</script>
