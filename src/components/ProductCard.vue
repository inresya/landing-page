<template>
    <div class="product-card">
      <img :src="image" alt="Product Image">
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ProductCard',
    props: ['title', 'description', 'image'],
  };
  </script>
  
  <style scoped>
  .product-card {
    border: 1px solid #ddd;
    border-radius: 5px;
    margin: 10px;
    padding: 10px;
    max-width: 200px;
    text-align: center;
  }
  .product-card img {
    width: 100%;
    height: auto;
    display: block;
  }
  </style>
  