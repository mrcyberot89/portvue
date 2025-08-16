<template>
    <div ref="containerRef" class=" absolute h-screen w-full z-0 justify-center flex bg-black">
        <video ref="videoRef" :src="cardFalling" playsinline muted @loadedmetadata="handleLoaded" @error="handleError"
            class=" object-cover"></video>
    </div>
</template>

<script>
import { ref, reactive } from 'vue';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);


import cardFalling from '../output.mp4';

export default {

    setup() {

        const videoRef = ref(null)
        const containerRef = ref(null)
        const state = reactive({
            isReady: false,
            errorMessage: ''
        })

        const handleLoaded = () => {
            if (videoRef.value && isFinite(videoRef.value.duration)) {
                state.isReady = true
                initScrollAnimation()
            }
        }

        const handleError = () => {
            state.errorMessage = 'Failed to load video'
        }

        const initScrollAnimation = () => {
            if (!videoRef.value || !containerRef.value) return
            gsap.to(videoRef.value, {
                scrollTrigger: {
                    trigger: containerRef.value,
                    start: "top top",
                    end: "bottom -100%",
                    scrub: 1,
                    pin: true,
                    smooth: 1,
                    // markers: true,
                    onUpdate: (self) => {
                        const time = videoRef.value.duration * self.progress
                        if (isFinite(time)) {
                            videoRef.value.currentTime = time
                        }
                    }
                },
                currentTime: videoRef.value.duration
            });


        }
        return { cardFalling, videoRef, containerRef, handleError, handleLoaded, initScrollAnimation }


    },

}

</script>
