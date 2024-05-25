<template>
  <div id="carousel-app">
    <div class="carousel-container">
      <transition-group class="carousel" tag="div" name="slide-fade" mode="out-in">
        <div v-if="currentIndex === 0" key="1" class="slide">
          <img src="../assets/best/best1.jpg" class="slide-image" alt="Slide 1" />
        </div>
        <div v-if="currentIndex === 1" key="2" class="slide">
          <img src="../assets/best/best2.jpg" class="slide-image" alt="Slide 2" />
        </div>
        <div v-if="currentIndex === 2" key="3" class="slide">
          <img src="../assets/best/best3.jpg" class="slide-image" alt="Slide 3" />
        </div>
        <div v-if="currentIndex === 3" key="4" class="slide">
          <img src="../assets/best/best4.jpg" class="slide-image" alt="Slide 4" />
        </div>
        <div v-if="currentIndex === 4" key="5" class="slide">
          <img src="../assets/best/best5.jpg" class="slide-image" alt="Slide 5" />
        </div>
        <div v-if="currentIndex === 5" key="6" class="slide">
          <img src="../assets/best/best6.jpg" class="slide-image" alt="Slide 6" />
        </div>
      </transition-group>
      <div class="dots">
        <span 
          v-for="(image, index) in images" 
          :key="'dot-' + index" 
          class="dot" 
          :class="{ active: currentIndex === index }" 
          @click="goToSlide(index)">
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Carousel',
  data() {
    return {
      images: [
        { src: '../assets/best/best1.jpg', alt: 'Slide 1' },
        { src: '../assets/best/best2.jpg', alt: 'Slide 2' },
        { src: '../assets/best/best3.jpg', alt: 'Slide 3' },
        { src: '../assets/best/best4.jpg', alt: 'Slide 4' },
        { src: '../assets/best/best5.jpg', alt: 'Slide 5' },
        { src: '../assets/best/best6.jpg', alt: 'Slide 6' }
      ],
      currentIndex: 0,
      interval: null,
    };
  },
  mounted() {
    this.startAutoSlide();
  },
  methods: {
    next() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    previous() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
    goToSlide(index) {
      this.currentIndex = index;
      this.resetAutoSlide();
    },
    startAutoSlide() {
      this.interval = setInterval(this.next, 3000);
    },
    stopAutoSlide() {
      clearInterval(this.interval);
    },
    resetAutoSlide() {
      this.stopAutoSlide();
      this.startAutoSlide();
    }
  },
  beforeDestroy() {
    this.stopAutoSlide();
  }
};
</script>

<style scoped>
h2 {
  font-size: 24px;
}

#carousel-app {
  border-radius: 4px;
  transition: all 0.2s;
  text-align: center;
  max-width: 100%;
  height: auto;
}

.carousel-container {
  border-radius: 5px;
  position: relative;
  overflow: hidden; /* Ensure no overflow */
  width: 100%;
  height: 600px;
}

.carousel {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  position: relative;
}

.slide {
  flex: 0 0 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 0;
  transition: opacity 0.5s ease;
  margin: 0;
  position: absolute;
  width: 100%;
  height: 100%;
}

.slide-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 15px;
}

.dots {
  position: absolute;
  bottom: 20px;
  width: 100%;
  display: flex;
  justify-content: center;
}

.dot {
  height: 15px;
  width: 15px;
  margin: 0 5px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
  cursor: pointer;
}

.dot.active {
  background-color: #717171;
}

.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: opacity 0.5s;
}

.slide-fade-enter,
.slide-fade-leave-to /* .slide-fade-leave-active in <2.1.8 */ {
  opacity: 0;
}
</style>

