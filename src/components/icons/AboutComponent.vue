<template>
    <div class=" h-screen w-full flex justify-center items-center bg-cover bg-top" :style="{backgroundImage: `url(${imagesTwo})`}">
        <div class="flex   container  h-full w-full justify-center items-center">
            <div class="  h-full md:h-1/2 w-full  -red-400 flex flex-col md:flex-row">
                <div class="w-full h-1/2 md:w-[40%] md:h-full flex justify-center py-4 px-4">
                   <img :src="imagesOne" alt="gambar1" class="object-cover h-full w-full  md:w-1/2  shadow-yellow-200">
                </div>
                <div ref="aboutContent" class="flex-col flex justify-center w-full md:w-1/2 items-start py-4 px-4 space-y-12 ">
                    <p class="text-white md:font-semibold text-2xl">About Me</p>
                    <p ref="about" class="text-white md:font-semibold md:text-lg">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Consectetur ipsam fugiat omnis? Minus voluptatum ipsa dolore error aliquid, eveniet maiores?Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae tempora rem omnis suscipit. Accusamus aperiam culpa possimus impedit, deleniti soluta. Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque consectetur quae vel accusantium. Accusantium provident laborum magnam. Deserunt, possimus eligendi.</p>
                </div>
            </div>
        </div>
    </div>
    
</template>

<script>
import { ref } from 'vue'
import imagesOne from '@/assets/gambar5.jpeg'
import imagesTwo from '@/components/icons/dark2.jpg'
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
import {SplitText} from 'gsap/all'



export default  {
    setup() {

        return { imagesOne, imagesTwo, ref };
    },
    mounted(){
        const about = this.$refs.about;
        const aboutContent = this.$refs.aboutContent;

        const paragraphSplit = new SplitText(about,{
            type: "lines",
        });

        gsap.from(paragraphSplit.lines, {
            opacity: 0,
            yPercent: 100,
            duration: 1.2,
            ease: 'expo.out',
            stagger: 0.06,
            scrollTrigger: {
                trigger: aboutContent,
                start: "top center",
                end: "bottom center",
                toggleActions: "play reverse play reverse",
                markers: true
            }
        });

    }
}
</script>