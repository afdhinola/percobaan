<template>
  <div class="home">
    <Hero />
    <Carousel />
  </div>
</template>

<script>
import Hero from '../components/Hero.vue';
import Carousel from '../components/Carousel.vue';

export default {
  name: 'Home',
  components : {
    Hero,
    Carousel,
  }
}
</script>

