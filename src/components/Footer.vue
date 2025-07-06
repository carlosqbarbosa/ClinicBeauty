<template>
  <footer class="bg-gray-900 text-white pt-16 py-8">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-12">
        <!--Informações da Clínica-->
        <section class="lg:col-span-2">
          <header class="flex items-center mb-6">
            <Icon icon="fa-solid:clinic-medical" class="text-3xl text-blue-500 mb-3" aria-hidden="true" />
            <h2 class="text-2xl font-bold ml-3">Clinic Beauty</h2>
          </header>
          <p class="text-gray-400 mb-4">
            Seu parceiro de confiança em beleza e bem-estar. Oferecemos uma variedade de serviços para ajudar você a se sentir e parecer o melhor possível.
          </p>
          <nav aria-label="Links de redes sociais">
            <ul class="flex space-x-4">
              <li v-for="(item, index) in socialLinks" :key="index">
                <a href="#" class="bg-gray-800 hover:bg-blue-600 w-10 h-10 rounded-full flex items-center justify-center transition" :aria-label="item.label">
                  <Icon :icon="item.icon" class="text-white text-lg" />
                </a>
              </li>
            </ul>
          </nav>
        </section>

        <!--Links Rápidos-->
        <section>
          <h3 class="text-lg font-semibold mb-4">Links Rápidos</h3>
          <ul class="space-y-2">
            <li><a href="#services" class="hover:text-blue-500 transition">Serviços</a></li>
            <li><a href="#about" class="hover:text-blue-500 transition">Sobre Nós</a></li>
            <li><a href="#specialists" class="hover:text-blue-500 transition">Nossos Especialistas</a></li>
            <li><a href="#contact" class="hover:text-blue-500 transition">Contato</a></li>
          </ul>
        </section>

        <!--Informações de Contato-->
        <address>
          <h3 class="text-xl font-bold mb-6 relative pb-2 after:content-[''] after:absolute after:left-0 after:bottom-0 after:w-12 after:h-1 after:bg-blue-500">
            Contato
          </h3>
          <ul class="space-y-3">
            <li v-for="(item, index) in contactInfo" :key="index" class="flex items-start">
              <Icon :icon="item.icon" class="text-blue-500 text-xl mt-1 mr-4 flex-shrink-0" />
              <component :is="item.content.type" v-bind="item.content.props" class="text-gray-400 hover:text-blue-500 transition">
                {{ item.content.text }}
              </component>
            </li>
          </ul>
        </address>
      </div>

      <!--Newsletter-->
      <section class="bg-gray-800 rounded-xl p-8 mb-12" aria-labelledby="newsletter-heading">
        <div class="flex flex-col lg:flex-row items-center justify-between">
          <div class="mb-6 lg:mb-0 lg:mr-8">
            <h3 id="newsletter-heading" class="text-xl font-bold mb-2">Assine nossa Newsletter</h3>
            <p class="text-gray-400">Fique por dentro das últimas novidades e promoções</p>
          </div>
          <form class="flex flex-col sm:flex-row w-full lg:w-auto" aria-label="Formulário de assinatura da newsletter">
            <label for="newsletter-email" class="sr-only">Seu endereço de e-mail</label>
            <input
              type="email"
              id="newsletter-email"
              name="email"
              required
              placeholder="Digite seu e-mail"
              class="px-6 py-3 rounded-full bg-gray-700 text-white focus:outline-none focus:ring-2 focus:ring-blue-500 mb-3 sm:mb-0 sm:mr-4 w-full"
              aria-required="true"
            />
            <button
              type="submit"
              class="bg-blue-600 hover:bg-blue-700 text-white px-8 py-3 rounded-full transition shadow-lg whitespace-nowrap"
              aria-label="Enviar formulário de contato"
            >
              Assinar
            </button>
          </form>
        </div>
      </section>

      <!--Legal-->
      <footer class="pt-8 border-t border-gray-800 flex flex-col md:flex-row justify-between items-center">
        <p class="text-gray-500 text-sm mb-4 md:mb-0">
          &copy; {{ currentYear }} Clinic Beauty. Todos os direitos reservados.
        </p>
        <nav aria-label="Links legais">
          <ul class="flex space-x-6">
            <li v-for="(link, index) in legalLinks" :key="index">
              <a href="#" class="text-gray-500 hover:text-blue-500 transition">{{ link.text }}</a>
            </li>
          </ul>
        </nav>
      </footer>
    </div>
  </footer>
</template>
<script setup>
import { Icon } from '@iconify/vue';
import { ref, computed } from 'vue';

const currentYear = computed(() => new Date().getFullYear());

const socialLinks = ref([
  { icon: 'fa-brands:facebook-f', label: 'Facebook' },
  { icon: 'fa-brands:twitter', label: 'Twitter' },
  { icon: 'fa-brands:instagram', label: 'Instagram' },
  { icon: 'fa-brands:linkedin-in', label: 'LinkedIn' },
  { icon: 'fa-brands:youtube', label: 'Youtube' }
]);

const contactInfo = ref([
  {
    icon: 'material-symbols:location-on',
    content: {
      type: 'a',
      props: {
        href: '#',
        target: '_blank',
        rel: 'noopener noreferrer'
      },
      text: 'Rua das Rosas, 123 - Jardim Bela Vista, São Paulo - SP, 01000-000'
    }
  },
  {
    icon: 'fa-solid:phone-alt',
    content: {
      type: 'a',
      props: {
        href: 'tel:+5511999998888'
      },
      text: '+55 (11) 99999-8888'
    }
  },
  {
    icon: 'fa-solid:envelope',
    content: {
      type: 'a',
      props: {
        href: 'mailto:contato@clinicbeauty.com.br'
      },
      text: 'contato@clinicbeauty.com.br'
    }
  },
  {
    icon: 'fa-solid:clock',
    content: {
      type: 'span',
      props: {},
      text: 'Seg - Sex: 08:00 às 19:00, Sáb: 09:00 às 14:00'
    }
  }
]);

const legalLinks = ref([
  { text: 'Política de Privacidade', href: '#privacy' },
  { text: 'Termos de Serviço', href: '#terms' },
  { text: 'Política de Cookies', href: '#cookies' }
]);
</script>
