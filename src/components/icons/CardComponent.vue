<template>
    <div class="relative bg-[#0f0e14] h-[300px] w-full mx-auto flex items-center justify-center overflow-hidden">
        <div class="justify-center gap-12 flex">
            <div ref="imageNin" class="h-[250px] w-[300px] bg-[#8a9295] rounded-t-md hidden cursor-pointer hover:bg-white" >
                <div class="flex justify-center py-4">
                    <p class="font-semibold">Front end developer</p>
                </div>
                <div class="flex justify-center">
                    <img :src="gambar9" alt="src" width="150px" class="">
                </div>
            </div>
            <div ref="imageTen" class="h-[250px] w-[300px] bg-[#8a9295] rounded-t-md hidden cursor-pointer hover:bg-white">
                <div class="flex justify-center py-4">
                    <p class="font-semibold">IT Support</p>
                </div>
                <div class="flex justify-center">
                    <img :src="gambar10" alt="src" width="150px" class="">
                </div>
            </div>
            <div ref="imageEl" class="h-[250px] w-[300px] bg-[#8a9295] rounded-t-md hidden cursor-pointer hover:bg-white">
                <div class="flex justify-center py-4">
                    <p class="font-semibold">Networking</p>
                </div>
                <div class="flex justify-center">
                    <img :src="gambar11" alt="src" width="150px" class="">
                </div>
            </div>
        </div>
    </div>
</template>
<script setup>
import gsap from 'gsap';
import { onMounted, ref } from 'vue';
import ScrollTrigger from 'gsap/ScrollTrigger';


import gambar9 from '@/assets/gambar9.png';
import gambar10 from '@/assets/gambar10.png';
import gambar11 from '@/assets/gambar11.png';

const imageNin = ref(null); //ref untuk animasi
const imageTen = ref(null); //ref untuk animasi
const imageEl = ref(null); //ref untuk animasi




onMounted(() => {
    gsap.registerPlugin(ScrollTrigger) //register untuk scroll

    //animasi untuk scroll
    gsap.fromTo(imageNin.value, {
        xPercent: -250,
    },
        {
            xPercent: 0,
            duration: 0.7,
            //stagger: 6,
            display: 'block',
            ease: 'power1.inOut',
            scrollTrigger: {
                markers: true,
                trigger: imageNin.value,
                start: 'top 60%',
                end: 'top 10%',
                toggleActions: 'play reverse play reverse'
            }
        }
    );
    gsap.fromTo(imageTen.value, {
        yPercent: 150,
    },
        {
            yPercent: 0,
            duration: 0.7,
            //stagger: 6,
            display: 'block',
            ease: 'power1.inOut',

            scrollTrigger: {
                //markers: true,
                trigger: imageTen.value,
                start: 'top 100%',
                end: 'top 50%',
                toggleActions: 'play reverse play reverse'
            }
        }
    );
    gsap.fromTo(imageEl.value, {
        xPercent: 250,
    },
        {
            xPercent: 0,
            duration: 0.7,
            //stagger: 6,
            display: 'block',
            ease: 'power1.inOut',
            scrollTrigger: {
                markers: true,
                trigger: imageEl.value,
                start: 'top 60%',
                end: 'top 10%',
                toggleActions: 'play reverse play reverse'
            }
        }
    );

});
</script>