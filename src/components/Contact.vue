<template>
  <section class="py-20 overflow-hidden bg-gradient-to-r from-pink-100 to-purple-100" id="contact">
    <div class="container mx-auto px-4">
      <!-- Section Header -->
      <header data-aos="fade-up" data-aos-delay="500" class="text-center mb-16">
        <h2 id="specialists-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
          Contact <span class="text-pink-600">Our Clinic</span>
        </h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Reach out to schedule your consultation or ask questions about services 
        </p>
      </header>
      <!--Main Contact-->
      <main class="flex flex-col lg:flex-row gap-12">
        <!--contact info-->
        <aside class="lg:w-2/5">
          <section class="bg-white rounded-2xl shadow-lg p-8 h-full">
            <h2 class="text-2xl font-bold text-gray-800 mb-6">Get in Touch</h2>
            <address class="space-y-6">
              <article
                  v-for="(item,index) in contactItems"
                  :key="index"
                  class="flex items-center bg-pink-100 px-4 py-3 rounded-full space-x-4"
                >
                  <figure class="bg-white p-2 rounded-full flex items-center justify-center">
                    <Icon :icon="item.icon" class="text-pink-600 text-xl" />
                  </figure>
                  <div class="flex-1">
                    <h3 class="font-semibold text-gray-800">{{ item.title }}</h3>
                    <div v-html="item.content" class="text-gray-600 text-sm"></div>
                  </div>
                </article>
            </address>
            <figure class="mt-8 rounded-xl overflow-hidden shadow-md">
              <img src="@assets/contactImg.jpg" alt="clinica"
              class="w-full h-68 object-cover hover:scale-105 transition-transform duration-500" 
              width="400" height="200" loading="lazy">
            </figure>
          </section>
        </aside>

        <!--contact form -->
        <section class="lg:w-3/5 flex-1">
          <div class="bg-white rounded-2xl shadow-lg p-8 h-full">
            <h2 class="text-2xl font-bold text-gray-800 mb-6">Contact Form</h2>
            <form action="#" method="POST" class="space-y-6">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                  <label for="name" class="block text-gray-700 mb-2">Your Name</label>
                  <input type="text" id="name" name="name" required 
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-pink-500">
                </div>
                <div>
                  <label for="email" class="block text-gray-700 mb-2">Your Email</label>
                  <input type="email" id="email" name="email" required 
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-pink-500">
                </div>
              </div>
              <div>
                <label for="service" class="block text-gray-700 mb-2">Select Service</label>
                <select id="service" name="service" v-model="services"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-pink-500">
                  <option v-for="service in services" :key="service.value" :value="service.value">{{ service.label }}</option>
                </select>
              </div>
              <div>
                <label for="message" class="block text-gray-700 mb-2">Your Message</label>
                <textarea id="message" name="message" rows="4" required 
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-pink-500"></textarea>
              </div>
              <button type="submit"
              class="w-full bg-pink-600 text-white font-semibold py-3 rounded-lg hover:bg-pink-700 transition-colors duration-300">
                Send Message
              </button>
            </form>

          </div>

        </section>
      </main>
    </div>
  </section>    
</template>

<script setup>
import { ref } from 'vue';
const contactItems = ref([
  {
    icon: 'fa-solid:map-marker-alt',
    title: 'Our Location',
    content: `<p>1123 Beauty Ave, Suite 456<br />Recife, Palmeiras</p>`
  },
  {
    icon: 'fa-solid:phone',
    title: 'Phone Number',
    content: `
      <p>
        Appointments: <a href='tel:+81123456778' class='hover:text-pink-600'>+81 1234 56778</a><br />
        Emergency: <a href='tel:+81123456779' class='hover:text-pink-600'>+81 1234 56779</a>
      </p>
    `
  },
  {
    icon: 'fa-solid:envelope',
    title: 'Email',
    content: `
      <p>
        <a href='mailto:info@gmail.com' class='hover:text-pink-600'>info@gmail.com</a>
      </p>
    `
  },
  {
    icon: 'fa-solid:clock',
    title: 'Working Hours',
    content: `
      <p>
        Sunday - Thursday: 9:00 AM - 8:00 PM <br />
        Friday: 2:00 PM - 9:00 PM
      </p>
    `
  }
]);
const services = ref([
  {value:'botox', label:'Botox Treatments'}, 
  {value:'fillers', label:'Dermal Fillers'}, 
  {value:'laser', label:'Laser Therapy'}, 
  {value:'facelift', label:'Non-Surgical Facelift'}, 
  {value:'other', label:'Others'}, 
]);
</script>