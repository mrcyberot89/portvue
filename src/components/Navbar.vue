<template>

    <nav class="fixed top-0 left-0 right-0  shadow-md z-50 bg-white/30  backdrop-blur-md ">
        <!-- Konten navbar -->
        <div class="container mx-auto px-4 py-3 flex justify-between items-center">
            <a href="#" class="text-white text-2xl font-bold">Logo</a>
            <div class="hidden md:flex space-x-6 text-white text-2xl font-semibold">
                <a href="#" class="hover:text-blue-500">Home</a>
                <a href="#" class="hover:text-blue-500">About</a>
                <a href="#" class="hover:text-blue-500">Services</a>
            </div>
            <div class="text-white hidden font-semibold md:block text-2xl">
                <a href="#" class="hover:text-blue-500">Contact</a>
            </div>
            <button class="md:hidden text-white">☰</button>
        </div>
    </nav>
</template>
<script>
import { ref, reactive } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger);

export default {
    mounted (){

    },
    setup (){

    }
}


</script>