<template>
  <section class="py-20 overflow-hidden bg-gradient-to-r from-blue-100 to-green-100" id="contact">
    <div class="container mx-auto px-4">
      <!-- Cabeçalho da Seção -->
      <header data-aos="fade-up" data-aos-delay="500" class="text-center mb-16">
        <h2 id="specialists-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
          Contato com a <span class="text-blue-600">Nossa Clínica</span>
        </h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Entre em contato para agendar sua consulta ou esclarecer dúvidas sobre nossos serviços.
        </p>
      </header>
      
      <!-- Conteúdo Principal -->
      <main class="flex flex-col lg:flex-row gap-12">
        <!-- Informações de Contato -->
        <aside class="lg:w-2/5">
          <section class="bg-white rounded-2xl shadow-lg p-8 h-full">
            <h2 class="text-2xl font-bold text-gray-800 mb-6">Fale Conosco</h2>
            <address class="space-y-6">
              <article
                v-for="(item, index) in contactItems"
                :key="index"
                class="flex items-center bg-blue-100 px-4 py-3 rounded-full space-x-4"
              >
                <figure class="bg-white p-2 rounded-full flex items-center justify-center">
                  <Icon :icon="item.icon" class="text-blue-600 text-xl" />
                </figure>
                <div class="flex-1">
                  <h3 class="font-semibold text-gray-800">{{ item.title }}</h3>
                  <div v-html="item.content" class="text-gray-600 text-sm"></div>
                </div>
              </article>
            </address>
            <figure class="mt-8 rounded-xl overflow-hidden shadow-md">
              <img src="@assets/contactImg.jpg" alt="Clínica"
                class="w-full h-68 object-cover hover:scale-105 transition-transform duration-500"
                width="400" height="200" loading="lazy">
            </figure>
          </section>
        </aside>

        <!-- Formulário de Contato -->
        <section class="lg:w-3/5 flex-1">
          <div class="bg-white rounded-2xl shadow-lg p-8 h-full">
            <h2 class="text-2xl font-bold text-gray-800 mb-6">Formulário de Contato</h2>
            <form action="#" method="POST" class="space-y-6">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                  <label for="name" class="block text-gray-700 mb-2">Seu Nome</label>
                  <input type="text" id="name" name="name" required
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                </div>
                <div>
                  <label for="email" class="block text-gray-700 mb-2">Seu E-mail</label>
                  <input type="email" id="email" name="email" required
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                </div>
              </div>
              <div>
                <label for="service" class="block text-gray-700 mb-2">Selecione o Serviço</label>
                <select id="service" name="service" v-model="services"
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                  <option v-for="service in services" :key="service.value" :value="service.value">{{ service.label }}</option>
                </select>
              </div>
              <div>
                <label for="message" class="block text-gray-700 mb-2">Sua Mensagem</label>
                <textarea id="message" name="message" rows="4" required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"></textarea>
              </div>
              <button type="submit"
                class="w-full bg-blue-600 text-white font-semibold py-3 rounded-lg hover:bg-blue-700 transition-colors duration-300">
                Enviar Mensagem
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
    title: 'Endereço',
    content: `<p>Rua Beauty, 1123, Sala 456<br />Recife, Palmeiras</p>`
  },
  {
    icon: 'fa-solid:phone',
    title: 'Telefone',
    content: `
      <p>
        Consultas: <a href='tel:+81123456778' class='hover:text-blue-600'>+81 1234 56778</a><br />
        Emergências: <a href='tel:+81123456779' class='hover:text-blue-600'>+81 1234 56779</a>
      </p>
    `
  },
  {
    icon: 'fa-solid:envelope',
    title: 'E-mail',
    content: `
      <p>
        <a href='mailto:info@gmail.com' class='hover:text-blue-600'>info@gmail.com</a>
      </p>
    `
  },
  {
    icon: 'fa-solid:clock',
    title: 'Horário de Atendimento',
    content: `
      <p>
        Domingo a Quinta: 9h às 20h <br />
        Sexta-feira: 14h às 21h
      </p>
    `
  }
]);
const services = ref([
  { value: 'botox', label: 'Tratamentos com Botox' },
  { value: 'fillers', label: 'Preenchimentos Faciais' },
  { value: 'laser', label: 'Terapia a Laser' },
  { value: 'facelift', label: 'Lifting Facial Não Cirúrgico' },
  { value: 'other', label: 'Outros' },
]);
</script>
