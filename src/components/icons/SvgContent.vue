<template>

    <div ref="containerDua" class="relative flex justify-center items-center h-screen w-full bg-[#313645] ">
        <div class="flex justify-center  items-center   h-1/2 w-[300px] absolute left-[35%]">
            <div ref="cardBack1" class="absolute   h-[450px] w-[300px] rounded-2xl transform-3d  -amber-500 -rotate-12">
                <div class="absolute   h-full w-full rounded-2xl overflow-hidden backface-hidden">
                    <img :src="kartuDua" alt="" class=" object-fill h-full w-full ">
                </div>
                <div
                    class="absolute h-full w-full text-white rounded-2xl bg-amber-300 text-2xl backface-hidden rotate-y-180">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo soluta neque beatae libero.
                        Temporibus, odit? Cumque pariatur ad fugiat facere.</p>
                </div>
            </div>
        </div>

        <div class="flex justify-center  items-center   h-1/2 w-[300px] ">
            <div ref="cardBack2" class="absolute   h-[450px] w-[300px] rounded-2xl transform-3d  -amber-500">
                <div class="absolute   h-full w-full rounded-2xl overflow-hidden backface-hidden">
                    <img :src="kartuDua" alt="" class=" object-fill h-full w-full ">
                </div>
                <div
                    class="absolute h-full w-full text-white rounded-2xl bg-amber-300 text-2xl backface-hidden rotate-y-180">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo soluta neque beatae libero.
                        Temporibus, odit? Cumque pariatur ad fugiat facere.</p>
                </div>
            </div>
        </div>
        <div class="flex justify-center  items-center   h-1/2 w-[300px] absolute left-[49%] ">
            <div ref="cardBack3" class="absolute   h-[450px] w-[300px] rounded-2xl transform-3d  -amber-500 rotate-12">
                <div class="absolute   h-full w-full rounded-2xl overflow-hidden backface-hidden">
                    <img :src="kartuDua" alt="" class=" object-fill h-full w-full ">
                </div>
                <div
                    class="absolute h-full w-full text-white rounded-2xl bg-amber-300 text-2xl backface-hidden rotate-y-180">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo soluta neque beatae libero.
                        Temporibus, odit? Cumque pariatur ad fugiat facere.</p>
                </div>
            </div>
        </div>

    </div>
    <div ref="contentSquare" class="h-screen w-full flex justify-center items-center">

    </div>
    <div ref="contentSquare" class="h-screen w-full flex justify-center items-center">

    </div>
</template>

<script>
import { ref } from 'vue';
import { gsap } from 'gsap/gsap-core';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

import cardImagesdua from '../../../public/backCard.png';


export default {
    mounted() {
        const square = this.$refs.square;
        const containerSquare = this.$refs.contentSquare;
        const containerDua = this.$refs.containerDua;
        const cardBack1 = this.$refs.cardBack1;
        const cardBack2 = this.$refs.cardBack2;
        const cardBack3 = this.$refs.cardBack3;
        const bungkusCard = this.$refs.bungkusCard;

        //contoh cardflip menggunakan gsap timeline

        const tl = gsap.timeline({
        
            scrollTrigger: {
                trigger: containerDua,
                start: 'bottom 97%',
                end: 'bottom 20%',
                scrub: 2,
                //markers: true,
                pin: containerDua,
            }

        });
        tl.to(cardBack1,{ xPercent : -100, rotate: 0});
        tl.to(cardBack3,{ xPercent: 100, rotate: 0});
        tl.to(cardBack1,{rotateY: 180,});   
        tl.to(cardBack2,{ rotateY: 180})
        tl.to(cardBack3,{rotateY: 180,});

        gsap.to (cardBack1,{
            duration: 1,
            repeat: -1,
            ease: 'power1.inOut',
            yoyo: true,
            y: 20
        });
        gsap.to (cardBack2,{
            duration: 1,
            repeat: -1,
            ease: 'power1.inOut',
            yoyo: true,
            y: 20
        });
        gsap.to (cardBack3,{
            duration: 1,
            repeat: -1,
            ease: 'power1.inOut',
            yoyo: true,
            y: 20
        })

    },
    setup() {
        const kartuDua = ref(cardImagesdua);
        return { kartuDua }
    },

}


</script>