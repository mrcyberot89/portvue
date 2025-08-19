<template> 
    <div ref="containerRef" class="relative h-screen w-full overflow-hidden  flex justify-center items-center z-10 bg-black">
        <div class=" container   h-1/2 w-full">
            <div class=" h-full w-full  grid grid-rows-3 ">
                <div ref="contactRef" class="mx-auto h-1/2 flex items-center justify-center">
                    <p class="text-white text-4xl font-bold ">Contact Me</p>
                </div>
                <div class=" h-1/2  w-full">
                    <p id="subtitle" class=" text-center text-white text-shadow-sm sm:text-lg md:text-2xl font-semibold">If you are looking to hire a
                        product designer,
                        I’m currently available for freelance work</p>
                </div>
                <div class="md:px-5 px-5 py-[-20px] justify-center items-center flex  text-black ">
                    <button
                        class="bg-[#9D9D9D] h-[50px] w-1/2 rounded-sm md:h-[30%] md:w-[20%] cursor-pointer md:rounded-md hover:bg-[#bf9b30]  hover:text-white">
                        <p class=" font-semibold text-sm">cybrtnox@gmail.com</p>
                    </button>
                </div>
            </div>
        </div>
    </div>
    <div class="border border-gray-500 h-[1px]">
    </div>
    <div class=" bg-black h-14 text-white flex items-center pl-7">
        <p>Made by Your Name — Copyright 2021</p>
    </div>
</template>

<script>
import { gsap } from 'gsap';
import { SplitText } from 'gsap/all';
import { ref } from 'vue';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

export default {
    mounted() {

        const subtitle = new SplitText("#subtitle", {
            type: "lines"
        });
        const containerRef = this.$refs.containerRef;
        const contactRef = this.$refs.contactRef;

        const tl = gsap.timeline({
            scrollTrigger: {
                trigger: containerRef,
                start: 'top 30%',
                end: 'bottom top',
                //scrub: true,
                toggleActions: 'play reverse play reverse',
               // markers: true

            }
        });
        tl.from(contactRef, { duration: 1, ease: 'power2.inOut', opacity: 0 });
        tl.from(subtitle.lines, {
            ease: 'expo.out',
            stagger: 0.5,
            duration: 0.5,
            scale: 0
        });
    },
    setup() {


    }










}

</script>