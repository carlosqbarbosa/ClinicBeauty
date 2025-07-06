<template>
  <section class="py-14 overflow-hidden bg-gradient-to-br from-pink-100 to-purple-100" id="about">
    <div class="container mx-auto px-4">
      <article
        data-aos="fade-up"
        data-aos-delay="400"
        class="flex flex-col lg:flex-row items-center gap-12"
      >
        <!--Image column-->
        <figure class="lg:w-5/12 relative">
          <div class="relative z-10 rounded-2xl overflow-hidden shadow-2xl w-full max-w-md mx-auto">
            <img
              :src="AboutImg"
              alt="about us"
              loading="lazy"
              class="max-w-md w-full h-auto object-cover aspect-[4/5] rounded-xl mx-auto"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent" aria-hidden="true"></div>
          </div>

          <!--Decorative Elements-->
          <span
            class="hidden lg:block absolute -bottom-8 -left-8 w-32 h-32 rounded-full bg-pink-500 opacity-20 z-0"
            aria-hidden="true"
          ></span>
          <span
            class="hidden lg:block absolute -top-8 -right-8 w-40 h-40 rounded-full bg-pink-600 opacity-20 z-0"
            aria-hidden="true"
          ></span>
        </figure>

        <!--Content Column-->
        <div data-aos="fade-up" data-aos-delay="600" class="lg:w-7/12">
          <header>
            <h2 id="about-heading" class="text-3xl lg:text-4xl font-bold text-gray-900 mb-6">
              About <span class="text-pink-600">Clinic Beauty</span>
            </h2>
            <p class="text-lg text-gray-600 mb-6">
              Welcome to Clinic Beauty, your premier destination for advanced skincare and beauty
              treatments. Our team of experienced professionals is dedicated to helping you achieve
              your beauty goals with personalized care and the latest technology.
            </p>
          </header>

          <section class="mb-8">
            <h3 class="text-2xl font-semibold text-gray-800 mb-4">Our Approach</h3>
            <ul class="space-y-3">
              <li v-for="(item, index) in approachItems" :key="index" class="flex items-start">
                <figure class="bg-pink-100 p-1 rounded-full mr-3">
                  <Icon :icon="item.icon" class="text-pink-600 text-xl" aria-hidden="true" />
                </figure>
                <p class="text-gray-700">{{ item.title }}</p>
              </li>
            </ul>
          </section>

          <!--Stats -->
          <section class="grid grid-cols-2 gap-4 mb-8">
            <article
              v-for="(item, index) in stats"
              :key="index"
              class="bg-white p-4 rounded-lg shadow-sm flex items-center"
            >
              <figure class="mr-3">
                <Icon :icon="item.icon" class="text-pink-500" aria-hidden="true" />
              </figure>
              <div>
                <strong class="text-xl font-bold text-gray-800">{{ item.value }}</strong>
                <p class="text-gray-600">{{ item.label }}</p>
              </div>
            </article>
          </section>

          <nav>
            <a
              href="#appointment"
              class="bg-pink-600 hover:bg-pink-700 text-white text-center px-6 py-3 rounded-full 
              inline-block transition shadow-md focus:outline-none focus:ring-2 focus:ring-pink-800 
              focus:ring-offset-2"
            >
              Meet Our Specialists
            </a>
          </nav>
        </div>
      </article>

      <!--Mission statement -->
      <aside class="mt-20 bg-white rounded-2xl p-8 md:p-12 shadow-lg relative overflow-hidden">
        <span
          class="absolute -top-20 -right-20 w-64 h-64 rounded-full bg-pink-500 opacity-40"
          aria-hidden="true"
        ></span>
        <div class="relative z-10">
          <h3 class="text-2xl font-bold text-gray-800 mb-6">Our Mission</h3>
          <blockquote class="text-lg text-gray-700 mb-6">
            <p>
              At Clinic Beauty, we are committed to providing exceptional care and innovative
              treatments that enhance your natural beauty. Our mission is to empower you with
              confidence and well-being through personalized skincare solutions.
            </p>
          </blockquote>
          <figure class="flex items-center">
            <div class="w-12 h-12 rounded-full bg-pink-100 flex items-center justify-center mr-4">
              <Icon icon="fa-solid:user-md" class="text-pink-600" aria-hidden="true" />
            </div>
            <figcaption>
              <cite class="text-gray-800">Dr. Jane Smith</cite>
              <p class="text-sm text-gray-600">Founder & Chief Dermatologist</p>
            </figcaption>
          </figure>
        </div>
      </aside>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
import AboutImg from '@/assets/about.jpg';

const approachItems = ref([
  {
    icon: 'fa-solid:heart',
    title: 'Personalized Care',
  },
  {
    icon: 'fa-solid:user-md',
    title: 'Medical Expertise',
  },
  {
    icon: 'fa-solid:clinic-medical',
    title: 'Modern Facilities',
  },
]);

const stats = ref([
  {
    icon: 'fa-solid:user',
    value: '500+',
    label: 'Happy Clients',
  },
  {
    icon: 'fa-solid:calendar-check',
    value: '1200+',
    label: 'Appointments',
  },
]);
</script>
