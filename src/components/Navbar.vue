<template>
    <nav class="fixed-navbar">
      <div class="navbar-container">
        <div class="top-bar">
          <div class="left-icons">
            <router-link to="/search">
              <img src="@/assets/search.png" alt="Search" class="search-icon" />
            </router-link>
          </div>
          <div class="logo">
            <router-link to="/">
              <img src="@/assets/logo.png" alt="Logo" />
            </router-link>
          </div>
          <div class="cart-icon">
            <router-link to="/cart">
              <img src="@/assets/cart.png" alt="Cart" />
            </router-link>
          </div>
        </div>
        <ul class="nav-links">
          <li><router-link to="/" exact-active-class="active-link">Home</router-link></li>
          <li><router-link to="/products" exact-active-class="active-link">Products</router-link></li>
          <li><router-link to="/about" exact-active-class="active-link">About</router-link></li>
          <li><router-link to="/contact" exact-active-class="active-link">Contact</router-link></li>
        </ul>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'Navbar'
  }
  </script>
  
  <style scoped>
  .fixed-navbar {
    position: fixed;
    top: 0;
    width: 100%;
    background-color: #fff; 
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    z-index: 1000;
    padding: 10px 0;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  }
  
  .navbar-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
    position: relative;
  }
  
  .top-bar {
    width: 100%;
    display: flex;
    justify-content: center; /* Center the logo */
    align-items: center;
    position: relative; /* Allow absolute positioning of search and cart icons */
  }
  
  .left-icons {
    position: absolute;
    left: 20px;
  }
  
  .search-icon {
    height: 18px;
  }
  
  .logo img {
    height: 40px;
  }
  
  .cart-icon {
    position: absolute;
    right: 20px;
  }
  
  .cart-icon img {
    height: 26px; 
  }
  
  .nav-links {
    list-style-type: none;
    margin: 10px 0 0 0;
    padding: 0;
    display: flex;
    justify-content: center;
    width: 100%;
  }
  
  .nav-links li {
    margin: 0 15px;
  }
  
  .nav-links a {
    text-decoration: none;
    color: #333; 
    padding: 10px 20px;
    display: block;
    font-weight: bold;
    position: relative;
  }
  
  .nav-links a::after {
    content: '';
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: -5px;
    width: 0;
    height: 3px;
    background-color: #333; 
    transition: width 0.3s;
  }
  
  .nav-links a:hover::after,
  .nav-links a.active-link::after {
    width: 100%;
  }
  
  .nav-links a.active-link {
    color: #333; 
  }
  </style>
  