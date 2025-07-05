<template>
    <header class=" relative bg-gradient-to-r from-pink-100 to-purple-100 ">
        <div class="max-w-screen-x1 mx-auto px-4 py-4 flex justify-between items-center">
            <!--logo-->
            <a href="/" class="flex items-center focus:outline-none focus:ring-2 focus:ring-pink-600 rounded">
                <h1 class="text-2xl font-extrabold tracking-wide text-pink-600">
                    Clinic Beauty
                </h1>
            </a>
            <!--Desktop navigation-->
            <nav class="hidden md:flex space-x-6" aria-label="Primary Navigation">
                <a v-for="(link, index) in navLinks" 
                :key="index" 
                href="link.href"
                class="text-gray-700 hover:text-pink-600 transition-colors duration-200 focus:outline-none
                focus:ring-2 focus:ring-pink-600 rounded">{{ link.label }}</a
                >
            </nav>
            <!--Appoinment Button (Desktop)-->
            <div class="hidden md:block">
                <a href="#appointment" 
                class="bg-pink-600 hover:bg-pink-700 text-white px-5 py-2 rounded-full transition-colors 
                duration-200 shadow-md focus:outline-none focus:ring-2 focus:ring-pink-800 focus:ring-offset-2">
                    Book Appointment
                </a>
            </div>
            <!--Mobile Menu Button-->
            <button class="md:hidden p-2 focus:outline-none focus:ring-2 focus:ring-pink-600 rounded"
            @click="toggleMenu" aria-label="Toggle menu"
            :aria-expanded="isMenuOpen.toString()" aria-controls="mobile-menu">
            <Icon :icon="isMenuOpen ? 'mdi:close' : 'mdi:menu' " class="w-6 h-6"/>
        </button>
        </div>
        <!--Mobile Menu-->
        <aside v-if="isMenuOpen" id="mobile-menu"
            class="md:hidden bg-white shadown-lg- py-4 px-4 absolute top-full left-0 right-0 z-40"
            aria-label="Mobile menu">
            <nav aria-label="Mobile Navigation">
                <ul class="flex flex-col space-y-4">
                    <li v-for="(link,index) in navLinks" :key="index">
                        <a :href="link.href"
                        class="block text-gray-700 hover:text-pink-600 transition-colors duration-200 py-2 px-2
                        focus:outline-none focus:ring-2 focus:ring-pink-600 rounded" @click="toggleMenu">
                        {{ link.label }}
                    </a>
                    </li>
                    <li>
                        <a href="#appointment" 
                        class="block bg-pink-600 hover:bg-pink-700 text-white text-center 
                        px-4 py-2 rounded-full transition-colors duration-200 shadow-md focus:outline-none 
                        focus:ring-2 focus:ring-pink-800 focus:ring-offset-2"
                        @click="toggleMenu">
                            Book Appointment
                        </a>
                    </li>
                </ul>
                
            </nav>
        </aside>
    </header>
</template>

<script setup>
import { ref } from 'vue';
const navLinks = ref([
    {href: '#home', label: 'Home'},
    {href: '#services', label: 'Services'},
    {href: '#about', label: 'About Us'},
    {href: '#contact', label: 'Contact'},
    {href: '#speciali', label: 'Our Specialties'},
]);
const isMenuOpen = ref(false);
const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
};

</script>
