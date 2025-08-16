<template>
    <div class="hover-box" @mouseenter="handleMouseEnter" @mouseleave="handleMouseLeave" ref="box">
        Hover Me!
    </div>
    <div class=" overflow-hidden text-2xl text-white flex justify-center items-center h-20 w-full container mx-auto">
        <p ref="paragrapj" v-on:mouseenter="mouseenter" v-on:mouseleave="mouseleave" class=" cursor-pointer">Lorem ipsum dolor, sit amet consectetur
            adipisicing elit. Et culpa earum placeat alias fugiat rem similique sed, possimus illo ratione.</p>
    </div>

</template>

<script>
import { gsap } from 'gsap';

export default {
    methods: {
        handleMouseEnter() {
            gsap.to(this.$refs.box, {
                scale: 1.1,
                backgroundColor: '#4CAF50',
                color: 'white',
                duration: 0.3,
                ease: 'power2.out'
            });
        },
        handleMouseLeave() {
            gsap.to(this.$refs.box, {
                scale: 1,
                backgroundColor: '#f5f5f5',
                color: '#333',
                duration: 0.3,
                ease: 'power2.out'
            });
        },
        mouseenter() {
            gsap.to(this.$refs.paragrapj, {
                ease: 'power2.out',
                duration: 0.3,
                if (onUpdate) {
                }
            });
        },
        mouseleave() {
            gsap.to(this.$refs.paragrapj, {
                ease: 'power2.in',
                duration: 0.3,
                color: '#f5f5f5',
                scale:1,
                y: 0,
            });
        }
    }
}
</script>

<style>
.hover-box {
    width: 200px;
    height: 200px;
    background: #f5f5f5;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 8px;
    cursor: pointer;
    transition: all 0.3s;
}
</style>