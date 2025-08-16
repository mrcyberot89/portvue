<template>

    <div ref="container" class=" h-[110vh] w-full flex flex-col gap-6 justify-center items-center relative mb-[100px] ">


        <div id="card"
            class=" flex flex-row   h-[70%] w-1/2  bg-gray-300/30 backdrop-blur-xl shadow-lg rounded-lg overflow-hidden  absolute ">
            <div ref="gambarOne" class="h-full w-full relative overflow-hidden ">
                <img :src="imagesOne" alt="img1" class="object-cover  h-full w-full">
            </div>
            <div class="text-white items-center justify-center w-full flex flex-col text-center px-8">
                <p class="font-semibold text-2xl"> Title Card </p>
                <p class=" font-medium text-lg ">Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Dignissimos similique harumam commodi quos cupiditate quo!</p>
            </div>
        </div>

        <div id="card2"
            class=" flex flex-row-reverse  h-[70%] w-1/2 bg-gray-300/30 backdrop-blur-xl shadow-lg rounded-lg overflow-hidden shadow-black absolute">
            <div class="h-full w-full relative">
                <img :src="imagesTwo" alt="img1" class="object-cover absolute h-full w-full">
            </div>
            <div class="text-white items-center justify-center w-full flex flex-col text-center  px-8">
                <p class=" font-semibold text-2xl"> Title Card </p>
                <p class=" font-medium text-lg">Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Dignissimos similique harum voluptas vitae, amet quaerat nam commodi quos cupiditate quo!</p>
            </div>
        </div>
        <div id="card3"
            class=" flex flex-row   h-[70%] w-1/2 bg-gray-500/70 backdrop-blur-xl shadow-lg rounded-lg overflow-hidden shadow-black absolute">
            <div class="h-full w-full relative">
                <img :src="imagesThree" alt="img1" class="object-cover absolute h-full w-full">
            </div>
            <div class="text-white items-center justify-center w-full flex flex-col text-center text-shadow-2xs text-shadow-black px-8">
                <p class=" font-semibold text-2xl "> Title Card </p>
                <p class=" font-medium text-lg ">Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Dignissimos similique harum voluptas vitae, amet quaerat nam commodi quos cupiditate quo!</p>
            </div>
        </div>



    </div>


</template>

<script>
import { ref } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

import imagesOne from '@/assets/gambar1.png';
import imagesTwo from '@/assets/gambar2.png';
import imagesThree from '@/assets/gambar3.png';
import imagesFour from '@/assets/gambar4.png';
import imagesFive from '@/assets/gambar5.png';
import imagesSix from '@/assets/gambar6.png';
import imagesSeven from '@/assets/gambar7.png';
export default {
    setup() {
        return {
            imagesOne,
            imagesTwo,
            imagesThree,
            imagesFour,
            imagesFive,
            imagesSix,
            imagesSeven
        }
    },
    mounted() {

        // Initialize GSAP animations or any other logic here
        const container = this.$refs.container;
        const imagesOne = this.$refs.gambarOne;


        gsap.timeline({
            scrollTrigger: {
                trigger: container,
                start: 'top 0%',
                end: 'bottom -50%',
                scrub: 1,
                //toggleActions: 'play reverse play reverse',
                markers: true,
                pin: true,
                pinSpacing: 0
            }
        }).from('#card', {
            y: '100vh',
            scale: 1,
            ease: 'power1.inOut',
            opacity: 0,

        }).to('#card', {
            y: -120,
            scale: 0.8,
            //opacity: '80%'
        }).from('#card2', {
            y: '100vh',
            scale: 1,
            duration: 1,
            ease: 'power1.inOut',
            opacity: 0

        }).to('#card2', {
            y: -60,
            scale: 0.9,
        }).from('#card3', {
            y: '100vh',
            scale: 1,
            ease: 'power1.inOut',
            opacity: 0
        });



        /*
        tl.to(card, {

           
            
            duration: 1,
            ease: 'power2.inOut',
            stagger: 0.2,
            scale: 0.8 + 0.2
        })
    */
    },

}





</script>
