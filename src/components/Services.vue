<template>
  <section
    id="services"
    class="py-20 overflow-hidden bg-gradient-to-r from-blue-100 to-green-100"
    aria-labelledby="services-heading"
  >
    <div class="container mx-auto px-4">
      <!-- Section Header -->
      <header data-aos="fade-up" data-aos-delay="500" class="text-center mb-16">
        <h2 id="services-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
          Beleza com <span class="text-blue-600">Sofisticação</span>
        </h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Conheça nossa linha de tratamentos estéticos especializados, pensados para realçar sua beleza natural e proporcionar bem-estar
        </p>
      </header>

      <!-- Services Grid -->
      <ul
        data-aos="fade-up"
        data-aos-delay="500"
        class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8"
      >
        <li v-for="(service, index) in services" :key="index">
          <article
            class="bg-white rounded-xl p-8 hover:shadow-lg transition-all duration-300 hover:-translate-y-1 h-full flex flex-col"
          >
            <figure class="mb-6">
              <Icon :icon="service.icon" class="text-4xl text-blue-600" aria-hidden="true" />
            </figure>
            <h3 class="text-xl font-bold text-gray-800 mb-3">
              {{ service.title }}
            </h3>
            <p class="text-gray-600 flex-grow">
              {{ service.description }}
            </p>
            <a
              :href="service.link"
              class="group inline-flex items-center gap-2 text-blue-600 font-semibold hover:text-blue-700 transition-colors mt-auto"
              :aria-label="`Learn more about ${service.title}`"
            >
              <span class="relative">
                Leia mais
                <span
                  class="absolute left-0 -bottom-0.5 w-full h-0.5 bg-blue-600 scale-x-0 group-hover:scale-x-100 transition-transform origin-left"
                ></span>
              </span>
              <Icon icon="weui:arrow-outlined" class="w-5 h-5 transition-transform group-hover:translate-x-1" />
            </a>
          </article>
        </li>
      </ul>

      <!-- CTA Section -->
      <footer data-aos="fade-up" data-aos-delay="600" class="mt-20 text-center">
        <h3 class="text-2xl font-bold text-gray-800 mb-6">Sua Transformação Começa Aqui</h3>
        <a
          href="#appointment"
          class="bg-blue-600 hover:bg-blue-700 text-white text-center px-8 py-3 rounded-full inline-block transition shadow-lg focus:outline-none focus:ring-2 focus:ring-blue-800 focus:ring-offset-2"
        >
          Agende agora uma consulta
        </a>
      </footer>
    </div>
  </section>
</template>

<script>
import { ref, onMounted } from 'vue';
import { Icon } from '@iconify/vue';
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  components: {
    Icon,
  },
  setup() {
    const services = ref([
      {
        icon: 'fa-solid:clinic-medical',
        title: 'Procedimentos Faciais',
        description:
          'Tratamentos faciais avançados que promovem rejuvenescimento, firmeza e uma aparência natural e saudável.',
        link: '#facelift',
      },
      {
        icon: 'fa-solid:user-md',
        title: 'Botox e Preenchimentos',
        description:
          'Reduza rugas e linhas de expressão com procedimentos minimamente invasivos, seguros e eficazes.',
        link: '#botox',
      },
      {
        icon: 'fa-regular:smile',
        title: 'Tratamentos a Laser',
        description:
          'Tecnologia a laser para rejuvenescimento, clareamento de manchas, remoção de pelos e muito mais.',
        link: '#laser',
      },
      {
        icon: 'fa-solid:syringe',
        title: 'Esculpimento Corporal',
        description:
          'Modelagem corporal com técnicas modernas para redefinir contornos e valorizar sua silhueta.',
        link: '#countouring',
      },
    ]);

    onMounted(() => {
      AOS.init();
    });

    return {
      services,
    };
  },
};
</script>

<style scoped>
/* Caso queira adicionar estilos personalizados */
</style>

