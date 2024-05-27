<template>
    <div class="carousel">
      <div class="carousel-inner" :style="{ transform: 'translateX(-' + currentIndex * 100 + '%)' }">
        <div class="carousel-item" v-for="(image, index) in images" :key="index">
          <img :src="image" alt="Carousel Image">
        </div>
      </div>
      <button class="carousel-control prev" @click="prevSlide">❮</button>
      <button class="carousel-control next" @click="nextSlide">❯</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Carousel',
    data() {
      return {
        currentIndex: 0,
        images: [
          new URL('@/assets/carousel1.jpg', import.meta.url).href,
          new URL('@/assets/carousel2.jpg', import.meta.url).href,
          new URL('@/assets/carousel3.jpg', import.meta.url).href,
        ],
      };
    },
    methods: {
      prevSlide() {
        this.currentIndex = (this.currentIndex + this.images.length - 1) % this.images.length;
      },
      nextSlide() {
        this.currentIndex = (this.currentIndex + 1) % this.images.length;
      },
    },
  };
  </script>
  
  <style scoped>
  .carousel {
    position: relative;
    width: 100%;
    overflow: hidden;
    margin-top: 60px;
  }
  .carousel-inner {
    display: flex;
    transition: transform 0.5s ease;
  }
  .carousel-item {
    min-width: 100%;
    box-sizing: border-box;
  }
  .carousel-item img {
    width: 100%;
    display: block;
  }
  .carousel-control {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    font-size: 2rem;
    cursor: pointer;
  }
  .prev {
    left: 10px;
  }
  .next {
    right: 10px;
  }
  </style>
  