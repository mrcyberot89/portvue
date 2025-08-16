<template>
    <div ref="containerCard" class=" relative h-screen w-full flex justify-center items-center">
        <!--cards-->
        <div 
            class="overflow-hidden  flex flex-col md:flex md:flex-row  md:flex-wrap gap-5 py-4 h-full w-full items-center justify-center   content-center">
            <div ref="cardOne" class="overflow-hidden h-40 w-[90%] md:h-2/6 md:w-[40%] bg-gray-800/50  rounded-2xl backdrop-blur-sm">

                <img ref="gambarOne" @mouseenter="mouseEnter" @mouseleave="mouseLeave" :src="gambar1" alt=""
                    class="object-cover h-1/2 w-1/2 float-left  rounded-lg mt-4 mx-4 ">
                <p class="text-white text-justify mx-4"> Lorem ipsum dolor sit, amet consectetur adipisicing elit. Amet,
                    odit dolores? Sed, incidunt non. Nostrum facere praesentium aut neque ipsum corporis harum.
                    Similique reiciendis asperiores officia praesentium sequi voluptatibus vel.Lorem ipsum dolor sit
                    amet consectetur adipisicing elit. Deleniti natus eos illum ducimus reiciendis, similique aperiam
                    facere ipsam neque et excepturi! Deleniti, repellat aut delectus iure labore unde distinctio modi
                    obcaecati quisquam ipsam cum dolor dolorum amet aperiam quae illo nihil tempore molestias quibusdam
                    veritatis ad impedit? Debitis, accusantium repellat?</p>

            </div>
            <div ref="cardTwo"
                class="overflow-hidden bg-gray-800/50 h-40 w-[90%] md:h-2/6 md:w-[40%]">

                <img :src="gambar2" alt="" class="object-cover h-[50%] w-1/2 float-left  rounded-lg mt-4 mx-4 ">
                <p class="text-white text-justify  mx-4"> lorem100Lorem ipsum dolor sit, amet consectetur adipisicing
                    elit. Amet, odit dolores? Sed, incidunt non. Nostrum facere praesentium aut neque ipsum corporis
                    harum. Similique reiciendis asperiores officia praesentium sequi voluptatibus vel.Lorem ipsum dolor
                    sit amet consectetur adipisicing elit. Deleniti natus eos illum ducimus reiciendis, similique
                    aperiam facere ipsam neque et excepturi! Deleniti, repellat aut delectus iure labore unde distinctio
                    modi obcaecati quisquam ipsam cum dolor dolorum amet aperiam quae illo nihil tempore molestias
                    quibusdam veritatis ad impedit? Debitis, accusantium repellat?</p>

            </div>
            <div ref="cardThree"
                class="overflow-hidden  bg-gray-800/50 h-40 w-[90%] md:h-2/6 md:w-[40%]">

                <img :src="gambar2" alt="" class="object-cover h-[50%] w-1/2 float-left rounded-lg mt-4 mx-4 ">
                <p class="text-white text-justify mx-4"> Lorem ipsum dolor sit, amet consectetur adipisicing elit. Amet,
                    odit dolores? Sed, incidunt non. Nostrum facere praesentium aut neque ipsum corporis harum.
                    Similique reiciendis asperiores officia praesentium sequi voluptatibus vel.Lorem ipsum dolor sit
                    amet consectetur adipisicing elit. Deleniti natus eos illum ducimus reiciendis, similique aperiam
                    facere ipsam neque et excepturi! Deleniti, repellat aut delectus iure labore unde distinctio modi
                    obcaecati quisquam ipsam cum dolor dolorum amet aperiam quae illo nihil tempore molestias quibusdam
                    veritatis ad impedit? Debitis, accusantium repellat?</p>

            </div>
            
        </div>
    </div>



</template>
<script>
import { ref } from 'vue';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);


import profile from '@/assets/profil.jpeg'
import gambar1 from '@/assets/gambar1.png'
import gambar2 from '@/assets/gambar2.png'

export default {

    methods: {

        mouseEnter() {
            gsap.to(this.gambarOne, {
                scale: 1.1,
                ease: 'power1.inOut',
                duration: 0.5,
            })
        },
        mouseLeave() {
            gsap.to(this.gambarOne, {
                scale: 1,
                duration: 0.5,
                ease: 'power1.inOut'
            })

        }

    },

    mounted() {
        const containerCard = this.$refs.containerCard;
        const cardOne = this.$refs.cardOne;
        const cardTwo = this.$refs.cardTwo;
        const cardThree = this.$refs.cardThree;
        const tl = gsap.timeline({
            //xPercent: 100,
            scrollTrigger: {
                triger: containerCard,
                start: 'top top',
                end: 'bottom top',
                scrub: true,
                pin: containerCard,
            }
        });
        tl.from(cardOne,{ scale:0, rotateY: 90 });
        tl.from(cardTwo,{ scale:0 });
        tl.from(cardThree,{ yPercent: 130, rotateY: 90});

    },
    setup() {

        //varibale ini digunaan untuk fungsi mouseenter dan mouseleave
        const gambarOne = ref(gambar1)
        const gambarTwo = ref(gambar2)

        return { profile, gambar1, gambar2, gambarOne, gambarTwo }


    }




}




</script>