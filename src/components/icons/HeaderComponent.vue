<template>
    <div class="relative flex  w-full h-screen md:px-20 px-[10px] overflow-hidden ">
        <div
            class=" container mx-auto grid grid-cols-1 md:grid md:grid-cols-2  md:gap-3 md:mt-32 relative h-[80%] w-full z-10  ">
            <div  ref="navigate"
                class=" text-[#bf9b30] flex absolute md:row-start-1 row-start-2 left-1/2 -translate-1/2 md:left-0 md:-translate-0 px-5 font-medium space-x-4 md:text-2xl ">
                <p class="hover:text-white" v-for="item in navigasiBar"><a href="#"> {{ item }}</a></p>

            </div>
            <div 
                class="text-white px-5 md:py-16 min-h-[100px] max-h-[500px] grid grid-cols-1 items-center justify-center ">
                <p ref="name" class="text-2xl  md:text-4xl text-center md:text-start lg:text-6xl font-bold">
                    I AM TORO product designer from Indonesia.</p>
                <p ref="nameDua" class=" font-medium md:text-2xl  text-gray-500 ">I help businesses and companies reach
                    their goals by designing user-centric digital
                    products & interactive experiences.</p>
            </div>
            <div class="grid  row-start-1 md:col-start-2 items-center justify-center md:justify-end ">
                <div ref="profile" @mouseenter="mouseenter" @mouseleave="mouseleave"
                    class=" cursor-pointer h-[200px] md:h-[300px] md:w-[300px] lg:h-[400px] lg:w-[400px] bg-cover">
                    <img ref="profileTor" :src="image" alt="profile"
                        class="object-cover w-full h-full rounded-full shadow-lg shadow-[#bf9b30]">
                </div>
            </div>
            <div class="md:px-5 px-5 py-0 items-center flex md:items-start justify-center md:justify-start  text-black">
                <button
                    class="bg-[#9D9D9D] shadow-lg shadow-[#000000] h-[50px] w-full rounded-sm md:h-[30%] md:w-[40%] cursor-pointer md:rounded-md hover:bg-[#bf9b30]  hover:text-white">
                    <p class=" font-semibold">cybrtnox@gmail.com</p>
                </button>
            </div>
        </div>
        <div class="absolute z-0 h-screen w-full  top-0 right-0">
            <img :src="dark1" alt="" class="object-cover h-screen w-full">
        </div>
    </div>
</template>
<style>
a::after {
    content: '';
    display: block;
    width: 0;
    height: 3px;
    background: hsl(163, 100%, 99%);
    transition: width .3s;
}

a:hover::after {
    width: 100%;
}
</style>

<script>
import { ref, onMounted } from 'vue'
import profile from '@/assets/profil.jpeg'
import { gsap } from 'gsap'
import { SplitText } from 'gsap/all'


import dark1 from '@/components/icons/dark2.jpg';



export default {
    methods: {
        mouseenter() {
            gsap.to(this.$refs.profileTor, {
                scale: 1.2,
                rotateY: 180,
                duration: 0.5,
                ease: 'power2.out',
            });
        },
        mouseleave() {
            gsap.to(this.$refs.profileTor, {
                scale: 1,
                rotateY: 360,
                duration: 0.5,
                ease: 'power2.out',
            })
        },
    },

    mounted() {
        /*
        const navigate = this.$refs.navigate;
        
        const profile = this.$refs.profile;
        const nameDua = this.$refs.nameDua;



        const paragraphSplitdua = new SplitText(nameDua, {
            type: "chars, words",
        });

        //animasi

        gsap.from(navigate, {
            duration: 1.5,
            x: -500,
            ease: 'power1.inOut',

            //scrub: 1,
        });
        
        gsap.from(paragraphSplitdua.words, {
            opacity: 0,
            yPercent: 100,
            duration: 2,
            ease: 'expo.out',
            stagger: 0.06,
            delay: 1,

        });

        gsap.from(profile, {
            opacity: 0,
            duration: 0.8,
            scale: 1.5,
            ease: 'power1.in',
        });
        
        
        const name = this.$refs.name;
        const paragraphSplit = new SplitText(name, {
            type: "lines, words"
        });

        gsap.from(paragraphSplit.lines, {
            opacity: 0,
            yPercent: 100,
            duration: 1.2,
            ease: 'expo.out',
            stagger: 0.09,
            delay: 1
        });
        */
    },

    //composisi api
    setup() {
        const image = ref(profile)
        const navigasiBar = ref([
            "Work",
            "About",
            "Contact",
            "Services"
        ])
        const navigate = ref(null)
        const animasiGsap = () => {
            gsap.from(navigate.value, {
                duration: 1.5,
                x: -500,
                //scale: 1,
                ease: 'power1.inOut',
            });
        };

       

        const name = ref(null);
        const nameDua = ref(null);

        const animasiSplitText = () => {
            if (name.value && nameDua.value) {
                const paragraphSplit = new SplitText(name.value, {
                    type: "lines, words"
                });
                const paragraphSplitDua = new SplitText(nameDua.value, {
                    type: "chars, words"
                });

                gsap.from(paragraphSplit.lines, {
                    opacity: 0,
                    yPercent: 100,
                    duration: 1.2,
                    ease: 'expo.out',
                    stagger: 0.09,
                    delay: 1
                });

                gsap.from(paragraphSplitDua.words, {
                    opacity: 0,
                    yPercent: 100,
                    duration: 2,
                    ease: 'expo.out',
                    stagger: 0.06,
                    delay: 1
                });
            }
        };

        onMounted(() => {
            animasiGsap();
            animasiSplitText();
        });

        return { image, dark1, navigasiBar, navigate, name, nameDua };
    
    }
}

</script>