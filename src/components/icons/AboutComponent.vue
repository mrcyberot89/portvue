<template>
    <div class=" h-screen w-full flex justify-center items-center bg-cover bg-top relative">
        <div class="flex   container  h-full w-full justify-center items-center z-10">
            <div class=" h-full md:h-1/2 w-full  -red-400 flex justify-center flex-col md:flex-row">
                <div  class="cursor-pointer w-full h-1/2 md:w-[40%] md:h-full flex justify-center py-4 px-4">
                   <img ref="imageCon" @mouseenter="mouseEnter" @mouseleave="mouseLeave" :src="imagesOne" alt="gambar1" class="object-cover h-full w-1/2  md:w-1/2 border border-gray-400 rounded-md ">
                </div>
                <div ref="aboutContent" class="flex-col flex justify-center w-full md:w-1/2 items-start py-4 px-4 space-y-12 ">
                    <p ref="title"  class="text-white md:font-semibold text-2xl">About Me</p>
                    <p ref="about" class="text-white md:font-semibold md:text-lg leading-7`">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Consectetur ipsam fugiat omnis? Minus voluptatum ipsa dolore error aliquid, eveniet maiores?Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae tempora rem omnis suscipit. Accusamus aperiam culpa possimus impedit, deleniti soluta. Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque consectetur quae vel accusantium. Accusantium provident laborum magnam. Deserunt, possimus eligendi.</p>
                </div>
            </div>
        </div>
        <div class=" h-full w-full z-0 absolute top-0 left-0">
            <img :src="bgOne" alt="bgImages" class="absolute  bottom-0 left-0 h-full w-full object-fill">
        </div>
    </div>
    
</template>

<script>
import { ref } from 'vue'
import imagesOne from '@/assets/gambar2.jpeg'
import imagesTwo from '@/components/icons/dark2.jpg'
import bgOne from '@/assets/bg2.png'
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
import {SplitText} from 'gsap/all'



export default  {
    setup() {

        return { imagesOne, imagesTwo, bgOne };
    },
    methods : {
        mouseEnter() {
            gsap.to(this.$refs.imageCon, {
                scale: 1.1,
                duration: 0.3
            });
        },
        mouseLeave() {
            gsap.to(this.$refs.imageCon, {
                scale: 1,
                duration: 0.3
            });
        }
    },
    mounted(){
        const about = this.$refs.about;
        const aboutContent = this.$refs.aboutContent;
        const titleAbout = this.$refs.title;

        const paragraphSplit = new SplitText(about,{
            type: "lines",
        });
        const titleSplit = new SplitText(titleAbout, {
            type: "chars, words",
        });
        gsap.from(titleSplit.words, {
            opacity: 0,
            yPercent: 100,
            //duration: 5,
            ease: 'expo.out',
            stagger: 0.06,
            //delay: 1,
            scrollTrigger: {
                trigger: aboutContent,
                start: "top 60%",
                end: "bottom 20%",
                toggleActions: "play reverse play reverse",
                markers: false
            }

        });

        gsap.from(paragraphSplit.lines, {
            opacity: 0,
            yPercent: 100,
            duration: 1.2,
            ease: 'expo.out',
            stagger: 0.06,
            delay: 1,
            scrollTrigger: {
                trigger: aboutContent,
                start: "top 60%",
                end: "bottom 20%",
                toggleActions: "play reset play reset",
                markers: false
            }
        });

        //image
        const imageCon = this.$refs.imageCon;
        gsap.from(imageCon, {
            opacity: 0,
            scale: 0,
            duration: 1.2,
            ease: 'expo.out',
            delay: 0.5,
            scrollTrigger: {
                trigger: imageCon,
                start: "top 80%",
                end: "bottom 10%",
                toggleActions: "play reset play reset",
                markers: true
            }
        });

    }
}
</script>