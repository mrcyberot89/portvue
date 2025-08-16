<template>



    <div ref="mainContainer"
        class="  bg-black/30 relative flex h-screen w-full overflow-hidden  justify-center items-center mx-auto ">
        <!--card 1-->
        <div class="absolute h-[450px] w-[300px]  top-1/2 left-1/2 -translate-x-[130%] -translate-y-[40%] z-0 ">
            <div class=" absolute h-full w-full transform transform-3d -rotate-[30deg] shadow-lg shadow-black"
                ref="cardFlip1" id="cardFlip">
                <div class="absolute w-full h-full backface-hidden rounded-2xl overflow-hidden">
                    <img :src="kartuDua" alt="" class=" object-fill h-full w-full">
                </div>
                <div
                    class="flex justify-center absolute  h-full w-full rounded-md bg-gray-200 shadow-lg shadow-black backface-hidden rotate-y-180 bg-gradient-to-tr from-[#bf9b30] to-black-300">
                    <div class=" mt-3 text w-full ">
                        <div class="text-center text-black ">
                            <p class=" text-3xl font-semibold">IoT</p>
                            <p class=" text-2xl ">(Internet Of Think)</p>
                        </div>

                        <div class="  text-black font-medium flex justify-center items-center mx-4 mt-18">
                            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis temporibus a debitis
                                iusto
                                quasi magni reprehenderit tempora, omnis harum sint?</p>
                        </div>
                    </div>
                </div>

            </div>
        </div>
        <!--Card 2-->
        <div class="absolute  h-[450px] w-[300px] top-1/2 left-1/2 -translate-x-[90%] -translate-y-1/2 z-10">
            <div class=" absolute h-full w-full transform transform-3d -rotate-[20deg] shadow-lg shadow-black"
                ref="cardFlip2">
                <div class="absolute h-full w-full rounded-2xl overflow-hidden  backface-hidden">
                    <img :src="kartuDua" alt="" class="object-fill h-full w-full">
                </div>
                <div
                    class="flex justify-center  absolute  h-full w-full rounded-md bg-gray-200 shadow-lg b shadow-black backface-hidden rotate-y-180 bg-gradient-to-tr from-[#bf9b30] to-black-300">
                    <div class=" m-3 text-center">
                        <p class=" text-3xl font-semibold text-black ">Front end Developer</p>
                        <div class="text-black font-medium mt-12 text-start  h-1/2 w-full flex items-center">
                            orem ipsum dolor sit amet consectetur adipisicing
                            elit.
                            Omnis corrupti assumenda eligendi ipsam, necessitatibus autem, ut perspiciatis dolores
                            animi
                            facere natus sunt minus totam voluptates eos itaque, dicta accusamus. Accusamus!</div>
                    </div>
                </div>
            </div>
        </div>
        <!--Card 3-->
        <div class="absolute  h-[450px] w-[300px] top-1/2 left-1/2 -translate-x-[50%] -translate-y-1/2 z-20 ">
            <div class=" absolute h-full w-full transform transform-3d rotate-0 shadow-lg shadow-black" ref="cardFlip3">
                <div class="absolute h-full w-full rounded-2xl overflow-hidden backface-hidden ">
                    <img :src="kartuDua" alt="" class=" object-fill h-full w-full">
                </div>
                <div
                    class="flex justify-center absolute  h-full w-full rounded-md bg-gray-200 shadow-lg shadow-black backface-hidden rotate-y-180 bg-gradient-to-tr from-[#bf9b30] to-black-300">
                    <div class=" m-3 text-center">
                        <p class=" text-3xl font-semibold text-black items-center">IT Technical</p>
                        <div class=" text-black font-medium text-start mt-24 flex justify-center h-1/2 items-center">
                            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam quibusdam sapiente
                                pariatur sed magni, repudiandae deleniti quisquam ducimus accusamus ullam! At omnis
                                veniam ipsam veritatis, doloribus mollitia officia aspernatur voluptatem?</p>
                        </div>
                    </div>

                </div>
            </div>
        </div>
        <!--Card 4-->
        <div class="absolute h-[450px] w-[300px]  top-1/2 left-1/2 -translate-x-[0%] -translate-y-1/2 z-30">
            <div class=" absolute h-full w-full transform transform-3d rotate-12 shadow-lg shadow-black" ref="cardFlip4"
                id="cardFlip">
                <div class="absolute w-full h-full backface-hidden rounded-2xl overflow-hidden">
                    <img :src="kartuDua" alt="" class=" object-fill h-full w-full">
                </div>
                <div
                    class="flex justify-center absolute  h-full w-full rounded-md bg-gray-200 shadow-lg shadow-black backface-hidden rotate-y-180 bg-gradient-to-tr from-[#bf9b30] to-black-300">
                    <div class=" mt-3 text w-full ">
                        <div class="text-center text-black ">
                            <p class=" text-3xl font-semibold">IoT</p>
                            <p class=" text-2xl ">(Internet Of Think)</p>
                        </div>

                        <div class="  text-black font-medium flex justify-center items-center mx-4 mt-18">
                            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis temporibus a debitis
                                iusto
                                quasi magni reprehenderit tempora, omnis harum sint?</p>
                        </div>
                    </div>
                </div>

            </div>
        </div>
        <!--card 5-->
        <div class="absolute h-[450px] w-[300px]  top-1/2 left-1/2 -translate-x-[-30%] -translate-y-[40%] z-30">
            <div class=" absolute h-full w-full transform transform-3d rotate-[25deg] shadow-lg shadow-black"
                ref="cardFlip5" id="cardFlip">
                <div class="absolute w-full h-full backface-hidden rounded-2xl overflow-hidden">
                    <img :src="kartuDua" alt="" class=" object-fill h-full w-full">
                </div>
                <div
                    class="flex justify-center absolute  h-full w-full rounded-md bg-gray-200 shadow-lg shadow-black backface-hidden rotate-y-180 bg-gradient-to-tr from-[#bf9b30] to-black-300">
                    <div class=" mt-3 text w-full ">
                        <div class="text-center text-black ">
                            <p class=" text-3xl font-semibold">IoT</p>
                            <p class=" text-2xl ">(Internet Of Think)</p>
                        </div>

                        <div class="  text-black font-medium flex justify-center items-center mx-4 mt-18">
                            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis temporibus a debitis
                                iusto
                                quasi magni reprehenderit tempora, omnis harum sint?</p>
                        </div>
                    </div>
                </div>

            </div>
        </div>

    </div>
    <!--container 2 example card
    <div  class="relative flex justify-center items-center h-screen w-full bg-[#313645] ">
        <div ref="containerDua"  class="absolute flex justify-center  items-center border h-1/2 w-[300px] ">
            <div ref="cardBack" class="absolute border h-[450px] w-[300px] rounded-2xl transform-3d border-amber-500"
                >
                <div class="absolute border h-full w-full rounded-2xl overflow-hidden backface-hidden">
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
    -->




</template>

<script>

//import { ref, reactive } from 'vue';
import { ref } from 'vue';
import gsap from 'gsap';
import { SplitText } from 'gsap/all';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);


//images
import cardImages from '@/components/icons/kartu.png';
import cardImagesdua from '../../../public/backCard.png';

export default {
    methods: {
        onMouseenter() {
            const CardFlip = document.querySelector('#cardFlip')

            gsap.to(CardFlip, {
                rotateY: 360,
                duration: 0.5,
                ease: 'power2.out'

            });
        },
        onMouseleave() {
            gsap.to("#cardFlip", {
                rotateY: 180,
                duration: 0.5,
                ease: 'power2.inOut'
            });
        }

    },

    mounted() {

        const mainContainer = this.$refs.mainContainer;
        const cardFlip1 = this.$refs.cardFlip1;
        const cardFlip2 = this.$refs.cardFlip2;
        const cardFlip3 = this.$refs.cardFlip3;
        const cardFlip4 = this.$refs.cardFlip4;
        const cardFlip5 = this.$refs.cardFlip5;
        const cardBack = this.$refs.cardBack;

        /*
     //example card flip
        gsap.to(cardBack, {
            rotateY: 180,
            scrollTrigger: {
                start: 'top 30%',
                end: '130% top',
                //markers: true,
                trigger: containerDua,
                //endTrigger: containerTiga,
                scrub: true,
                //pin harus di arahkan ke pembungkus dari animasinya yg dimana animasinya adalah containerDua atau sama dengan trigernya
                pin: true,
             
                

            }
        });
        
        */

        gsap.to(cardFlip1, {
            xPercent: -150,
            rotate: 0,
            ease: 'power2.inOut',


            scrollTrigger: {
                trigger: mainContainer,
                ///endTrigger: containerDua,
                start: 'top 30%',
                end: 'bottom 70%',
                toggleActions: 'play reverse play reverse',



            }
        });
        gsap.to(cardFlip1, {
            rotateY: 180,
            ease: 'power2.inOut',
            duration: 0.2,
            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 30px',
                end: 'bottom 70%',
                toggleActions: 'play reverse play reverse',


            }
        });
        gsap.to(cardFlip1, {
            duration: 1,
            yoyo: true,
            y: 20,
            repeat: -1,
            ease: 'power1.inOut'
        });

        gsap.to(cardFlip2, {
            xPercent: -75,
            yPercent: 10,
            rotate: 0,
            ease: 'power2.inOut',


            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 10px',
                end: 'top bottom',
                start: 'top 30%',
                end: 'bottom 70%',
                toggleActions: 'play reverse play reverse',
            }
        });
        gsap.to(cardFlip2, {
            rotateY: 180,
            ease: 'power2.inOut',
            duration: 0.4,
            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 30px',
                end: 'bottom 70%',
                toggleActions: 'play reverse play reverse',
                //markers: true,

            }
        });
        gsap.to(cardFlip2, {
            duration: 1,
            yoyo: true,
            y: 20,
            repeat: -1,
            ease: 'power1.inOut'
        });

        //card3
        gsap.to(cardFlip3, {
            xPercent: 0,
            yPercent: 10,
            rotate: 0,
            ease: 'power2.inOut',
            duration: 1,

            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 30%',
                end: 'bottom 70%',
                //scrub: 2,
                //markers: true,
                //pin: true,
                toggleActions: 'play reverse play reverse',
            }
        });

        gsap.to(cardFlip3, {
            rotateY: 180,
            ease: 'power2.inOut',
            duration: 0.6,
            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 30px',
                end: 'bottom 70%',
                toggleActions: 'play reverse play reverse',
                //markers: true,

            }
        });
        gsap.to(cardFlip3, {
            duration: 1,
            yoyo: true,
            y: 20,
            repeat: -1,
            ease: 'power1.inOut'
        });

        //card 4
        gsap.to(cardFlip4, {
            xPercent: 65,
            yPercent: 10,
            rotate: 0,
            ease: 'power2.inOut',
            duration: 0.5,

            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 30%',
                end: 'bottom 70%',
                //scrub: 2,
                //markers: true,
                //pin: true,
                toggleActions: 'play reverse play reverse',
            }
        });
        gsap.to(cardFlip4, {
            rotateY: 180,
            ease: 'power2.inOut',
            duration: 0.8,
            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 30px',
                end: 'bottom 70%',
                toggleActions: 'play reverse play reverse',
                //markers: true,

            }
        });
        gsap.to(cardFlip4, {
            duration: 1,
            yoyo: true,
            y: 20,
            repeat: -1,
            ease: 'power1.inOut'
        });

        //card 5
        gsap.to(cardFlip5, {
            xPercent: 150,
            yPercent: 0,
            rotate: 0,
            ease: 'power2.inOut',
            duration: 0.5,

            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 30%',
                end: 'bottom 70%',
                //scrub: 2,
                //markers: true,
                //pin: true,
                toggleActions: 'play reverse play reverse',
            }
        });
        gsap.to(cardFlip5, {
            rotateY: 180,
            ease: 'power2.inOut',
            duration: 1,
            scrollTrigger: {
                trigger: mainContainer,
                start: 'top 30px',
                end: 'bottom 70%',
                toggleActions: 'play reverse play reverse',
                //markers: true,

            }
        });
        gsap.to(cardFlip5, {
            duration: 1,
            yoyo: true,
            y: 20,
            repeat: -1,
            ease: 'power1.inOut'
        });







    },

    setup() {
        const kartu = ref(cardImages);
        const kartuDua = ref(cardImagesdua);
        return { kartu, kartuDua }
    },
}



</script>