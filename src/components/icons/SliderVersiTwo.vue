<template>
    <div class="h-screen relative overflow-hidden bg-black">
        <div class="container">

            <div class="slide">


                <div class="item" :style="{ backgroundImage: `url(${imagesOne})` }">
                    

                </div>
                <div class="item" :style="{ backgroundImage: `url(${imagesTwo})` }">
                    

                </div>
                <div class="item" :style="{ backgroundImage: `url(${imagesThree})` }">
                    

                </div>
                <div class="item" :style="{ backgroundImage: `url(${imagesFour})` }">
                    

                </div>
                <div class="item" :style="{ backgroundImage: `url(${imagesFive})` }">
                    

                </div>
                <div class="item" :style="{ backgroundImage: `url(${imagesSix})` }">
                   

                </div>


            </div>

            <div class="button">
                <button @click="prevSlide">❮</button>
                <button @click="nextSlide">❯</button>
            </div>

        </div>
    </div>


</template>

<style scoped>
.container {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 1000px;
    height: 600px;
    background: #f5f5f5;
    box-shadow: 0 30px 50px #dbdbdb;
}

.item {
    width: 200px;
    height: 300px;
    position: absolute;
    top: 50%;
    transform: translate(0, -50%);
    border-radius: 20px;
    box-shadow: 0 30px 50px #505050;
    background-position: 50% 50%;
    background-size: cover;
    display: inline-block;
    transition: 0.5s;
}

.item:nth-child(1),
.item:nth-child(2) {
    top: 0;
    left: 0;
    transform: translate(0, 0);
    border-radius: 0;
    width: 100%;
    height: 100%;
    /*scale: 2; */
    
}


.item:nth-child(3) {
    left: 50%;
}

.item:nth-child(4) {
    left: calc(50% + 220px);
}

.item:nth-child(5) {
    left: calc(50% + 440px);
}

/* here n = 0, 1, 2, 3,... */
.item:nth-child(n + 6) {
    left: calc(50% + 660px);
    opacity: 0;
}


/*
.item .content{
    position: absolute;
    top: 50%;
    left: 100px;
    width: 300px;
    text-align: left;
    color: #eee;
    transform: translate(0, -50%);
    font-family: system-ui;
    display: none;
}


.slide .item:nth-child(2) .content{
    display: block;
}


.content .name{
    font-size: 40px;
    text-transform: uppercase;
    font-weight: bold;
    opacity: 0;
    animation: animate 1s ease-in-out 1 forwards;
}

.content .des{
    margin-top: 10px;
    margin-bottom: 20px;
    opacity: 0;
    animation: animate 1s ease-in-out 0.3s 1 forwards;
}

.content button{
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    opacity: 0;
    animation: animate 1s ease-in-out 0.6s 1 forwards;
}
*/

@keyframes animate {
    from{
        opacity: 0;
        transform: translate(0, 100px);
        filter: blur(33px);
    }

    to{
        opacity: 1;
        transform: translate(0);
        filter: blur(0);
    }
}



.button {
    width: 100%;
    text-align: center;
    position: absolute;
    bottom: 20px;
}

.button button {
    width: 40px;
    height: 35px;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    margin: 0 5px;
    border: 1px solid #000;
    transition: 0.3s;
    background: white;
}

.button button:hover {
    background: #ababab;
    color: #fff;
}
</style>

<script>
import gsap from 'gsap';
import { ref } from 'vue';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);


import imagesOne from '@/assets/gambar1.png';
import imagesTwo from '@/assets/gambar2.png';
import imagesThree from '@/assets/gambar3.png';
import imagesFour from '@/assets/gambar4.png';
import imagesFive from '@/assets/gambar5.png';
import imagesSix from '@/assets/gambar6.png';
import imagesSeven from '@/assets/gambar7.png';
export default {

    methods: {
        nextSlide() {
            let item = document.querySelectorAll('.item');
            document.querySelector('.slide').appendChild(item[0]);
        },
        prevSlide() {
            let item = document.querySelectorAll('.item');
            document.querySelector('.slide').prepend(item[item.length - 1]);
        },
    },


    setup() {


        return {
            imagesOne, imagesTwo, imagesThree, imagesFour, imagesFive, imagesSix, imagesSeven
        }
    },
    mounted() {

    }
}

</script>