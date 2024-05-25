<template>
    <div class="hero">
      <div class="image-container">
        <img src="@/assets/hero.jpg" alt="Home" class="store-image" />
        <div class="banner-text">
          <h2>Misolo Cosmetics</h2>
          <p>LEARN ABOUT OUR ANTI-AGING, FIRMING AND REGULATING PRODUCTS. 99% NATURAL</p>
          <router-link to="/products"> <button>SHOP NOW</button> </router-link>
        </div>
      </div>
      <h1>THE BEST OF MISOLO</h1>
    </div>
  </template>
  
  <script>
  import { RouterLink } from 'vue-router';

  export default {
    name: 'Hero'
  }
  </script>
  
  <style scoped>
  .hero {
    text-align: center;
    padding: 50px 0;
    margin-top: 45px;
  }
  
  .image-container {
    position: relative;
    max-width: 100%;
    text-align: center;
    color: white;
  }
  
  .store-image {
    width: 100%;
    height: auto;
    display: block;
  }
  
  .banner-text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: transparent;
    padding: 20px;
    border-radius: 10px;
  }
  
  .banner-text h2 {
    margin: 0;
    font-size: 50px;
    font-family: sans-serif;
  }
  
  .banner-text p {
    margin: 0;
    font-size: 12px;
    margin-top: 10px;
  }
  
  button {
    margin: 0;
    padding: 15px;
    width: 150px;
    font-size: 15px;
    color: aliceblue;
    font-family: sans-serif;
    background-color: transparent;
    margin-top: 20px;
    border: solid 1px white;
    border-radius: 10px;
  }
  </style>
  