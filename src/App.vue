<template>
  <div>
    <TheHeader/>
    <Hero />
  </div>
</template>
<script setup>

import {onMounted} from 'vue';
import TheHeader from './components/TheHeader.vue';
import Hero from './components/Hero.vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
onMounted(() => {
  AOS.init();
});
</script>
<style>
</style>