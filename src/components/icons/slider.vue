<template>
  <div class=" bg-black h-screen w-full justify-center items-center flex">
    <div class="slider-container">
      <div class=" flex transition-transform" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
        <div v-for="(slide, index) in slides" :key="index" class="relative min-w-full" :class="{ active: currentIndex === index }">
          <img :src="slide.image" :alt="slide.title">
          <div class="slide-content">
            <h3>{{ slide.title }}</h3>
            <p>{{ slide.description }}</p>
          </div>
        </div>
      </div>
  
      <button @click="prevSlide" class="slider-btn prev">❮</button>
      <button @click="nextSlide" class="slider-btn next">❯</button>
      <div class="slider-dots">
        <span v-for="(dot, index) in slides" :key="index" @click="goToSlide(index)"
          :class="{ active: currentIndex === index }"></span>
      </div>
  
    </div>
  </div>
</template>

<script>
import images1 from '@/assets/gambar1.png'
import images2 from '@/assets/gambar2.png'
import images3 from '@/assets/profil.jpeg'

export default {
  data() {
    return {
      currentIndex: 0,
      slides: [
        {
          image: images1,
          title: 'Slide Pertama',
          description: 'Ini adalah deskripsi untuk slide pertama Lorem ipsum dolor, sit amet consectetur adipisicing elit. Consectetur vero impedit in soluta voluptatem laborum velit incidunt excepturi, distinctio ut.'
        },
        {
          image: images2,
          title: 'Slide Kedua',
          description: 'Ini adalah deskripsi untuk slide kedua'
        },
        {
          image: images1,
          title: 'Slide Ketiga',
          description: 'Ini adalah deskripsi untuk slide ketiga'
        }
      ],
      autoPlay: null
    }
  },
  methods: {
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.slides.length;
    },
    prevSlide() {
      this.currentIndex = (this.currentIndex - 1 + this.slides.length) % this.slides.length;
    },
    goToSlide(index) {
      this.currentIndex = index;
    },

  },

}
</script>

<style scoped>
.slider-container {
  position: relative;
  width: 100%;
  max-width: 800px;
  margin: 0 auto;
   overflow: hidden;
}

/*
.slider {
  display: flex;
  transition: transform 0.5s ease-in-out;
}
.slide {
  min-width: 100%;
  position: relative;
}

*/
.slide img {
  width: 100%;
  display: block;
}

.slide-content {
  position: absolute;
  bottom: 20px;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 20px;
}

.slider-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  padding: 10px 15px;
  cursor: pointer;
  font-size: 18px;
  z-index: 10;
}

.slider-btn:hover {
  background: rgba(0, 0, 0, 0.8);
}

.prev {
  left: 10px;
}

.next {
  right: 10px;
}

.slider-dots {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 10px;
}

.slider-dots span {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.5);
  cursor: pointer;
}

.slider-dots span.active {
  background: white;
}
</style>