<template>
  <section class="py-20 overflow-hidden bg-gradient-to-r from-pink-100 to-purple-100" id="specialists">
    <div class="container mx-auto px-4">
      <!-- Section Header -->
      <header data-aos="fade-up" data-aos-delay="500" class="text-center mb-16">
        <h2 id="specialists-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
          Meet Our <span class="text-pink-600">Specialists</span>
        </h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Our team of experts is dedicated to providing you with the highest quality care and personalized treatments.
        </p>
      </header>

      <!-- Specialists Grid -->
      <ul data-aos="fade-up" data-aos-delay="500" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
        <li v-for="doctor in specialists" :key="doctor.id" class="group relative">
          <article class="bg-white rounded-xl shadow-lg overflow-hidden hover:shadow-xl transition-all duration-300 h-full">
            <figure class="relative h-[340px] md:h-[300px] lg:h-[280px] overflow-hidden">
              <img :src="doctor.image" :alt="doctor.name"
                class="w-full h-full object-cover object-top transition-transform duration-500 group-hover:scale-105"
                loading="lazy">
              <span class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent" aria-hidden="true"></span>
              <aside class="absolute top-4 right-4 bg-white/90 px-3 py-1 rounded-full flex items-center shadow-sm"
                :aria-label="`Rating: ${doctor.rating} stars`">
                <Icon v-for="i in 5" :key="i"
                  :icon="i <= doctor.rating ? 'mdi:star' : 'mdi:star-outline'"
                  class="text-yellow-400 inline" />
                <span class="ml-1 text-sm font-medium">{{ doctor.rating }}.0</span>
              </aside>
            </figure>
            <div class="p-6 relative -m-10">
              <div class="bg-pink-50 rounded-lg shadow-md p-6">
                <header>
                  <h3 class="text-xl font-bold text-gray-800 mb-1">{{ doctor.name }}</h3>
                  <p class="text-pink-600 font-medium mb-3">{{ doctor.role }}</p>
                </header>
                <p class="text-gray-600 mb-4">{{ doctor.bio }}</p>
                <ul class="flex flex-wrap gap-2 mb-4">
                  <li v-for="(spec, i) in doctor.specialities" :key="i">
                    <span class="bg-pink-50 text-pink-600 text-xs font-medium px-3 py-1 rounded-full">
                      {{ spec }}
                    </span>
                  </li>
                </ul>
                <!--
                <figure class="absolute -top-6 left-6 bg-pink-600 text-white p-3 rounded-full shadow-lg" aria-hidden="true">
                  <Icon icon="mdi:format-quote-open" class="text-lg" />
                </figure>
                -->
              </div>
            </div>
          </article>
        </li>
      </ul>

      <!-- CTA Section -->
      <aside class="bg-gradient-to-r from-pink-100 to-purple-100 rounded-2xl p-8 md:p-12 text-center relative
      overflow-hidden" data-aos="fade-up" data-aos-delay="500">
        <span class=" absolute -top-20 -left-20 w-40 h-40 rounded-full bg-pink-200 opacity-20" aria-hidden="true"></span>
        <span class=" absolute -bottom-20 -right-20 w-60 h-60 rounded-full bg-purple-200 opacity-20" aria-hidden="true"></span>
        <div class="relative z-10">
            <h3 class="text-2x1 md:text-3x1 font-bold text-gray-800 mb-6">
                Ready to Consult with Our Specialists?
            </h3>
            <p class="text-lg text-gray-600 mb-8 max-w-2x1 mx-auto">
                Book a personalized consultation to discuss your Aesthetic goals and treatments options
            </p>
            <nav class="flex flex-col sm:flex-row justify-center grap-4">
            <a
              href="#appointment"
              class="bg-pink-600 hover:bg-pink-700 text-white text-center px-6 py-3 rounded-full 
              inline-block transition shadow-md focus:outline-none focus:ring-2 focus:ring-pink-800 
              focus:ring-offset-2"
            >
              Book Consultation
            </a>
            <a href="#contact"
                class="border border-pink-600 text-pink-600 hover:bg-pink-50
                 px-8 py-3 rounded-full transition focus:outline-none focus:ring-2 focus:ring-pink-500 
                focus:ring-offset-2" aria-label="Contact us">Contact Us</a>
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
    name: 'Dr. Jane Alvez',
    role: 'Aesthetic Dermatology',
    image: Image1,
    bio: 'Specialist in facial treatments, peels, and rejuvenation. Focused on natural results and patient well-being.',
    specialities: ['Peels', 'Facial Cleansing', 'Facial Rejuvenation'],
    rating: 5
  },
  {
    id: 2,
    name: 'Dr. Michael Cabello',
    role: 'Facial Harmonization',
    image: Image2,
    bio: 'Passionate about enhancing each patient’s natural beauty through modern filler and botulinum toxin techniques.',
    specialities: ['Facial Fillers', 'Botulinum Toxin', 'Facial Contouring'],
    rating: 5
  },
  {
    id: 3,
    name: 'Dr. Emily Braga',
    role: 'Aesthetics and Cosmetology',
    image: Image3,
    bio: 'Performs facial cleansing, lymphatic drainage, and body treatments focused on results and relaxation.',
    specialities: ['Facial Cleansing', 'Lymphatic Drainage', 'Body Treatments'],
    rating: 5
  }
]);
</script>