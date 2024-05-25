// src/views/Products.vue
<template>
  <div>
    <h1>Our Products</h1>
    <div v-for="product in products" :key="product.id">
      <h2>{{ product.name }}</h2>
      <p>{{ product.description }}</p>
      <p>{{ product.price }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        { id: 1, name: 'Product 1', description: 'Description 1', price: '$10' },
        { id: 2, name: 'Product 2', description: 'Description 2', price: '$20' }
      ]
    }
  }
}
</script>

<style scoped>
/* Add styles for the products page */
</style>
