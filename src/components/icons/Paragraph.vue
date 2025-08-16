<template>
    
    <div class="relative  h-screen w-full flex justify-center items-center overflow-hidden " ref="containerTiga">
        <div class="container z-10 text-4xl font-semibold text-white  font-mono ">
            <p id="subtitle" class=" text-shadow text-shadow-lg text-shadow-black/50 space-y-6 text-center ">
                aku juga mencintai manusia bukan hanya individu tertentu
                tetapi semua orang. tetapi
                aku mencintai mereka dengan kesadaran egoisme, aku mencintai mereka karena cinta membuatku bahagia, aku
                mencintai karena mencintai adalah sesuatu yang alami bagiku, karena itu menyenangkanku. Aku tidak
                mengenal perintah 'cinta'. aku memiliki rasa persaudaraan dengan setiap makhluk yang memiliki perasaan,
                penderitaan mereka adalah penderitaanku, kebahagiaan mereka adalah kebahagiaanku juga.</p>
        </div>

    </div>
    

</template>
<script>
//import { ref, reactive } from 'vue';
import { ref, reactive } from 'vue';
import { gsap } from 'gsap';
import { SplitText } from 'gsap/all';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

import cardAs from '@/components/icons/cardAs1.png';

export default {
    mounted() {

        const containerTiga = this.$refs.containerTiga;
        const asTwo =this.$refs.asTwo;

        const paragraphSplit = new SplitText("#subtitle", {
            //type: "words, chars",
            type: "lines"
        });

        gsap.from(paragraphSplit.lines, {
            //x: 100,
            //duration: 1,
            ease: 'expo.out',
            stagger: 0.10,
            opacity: 0,

            scrollTrigger: {
                trigger: containerTiga,
                start: '20% center',
                end: 'bottom center',
                toggleActions: 'play reverse play reverse',
                markers: true
            }
        });

 


    },
    setup() {

        


    },

}

</script>