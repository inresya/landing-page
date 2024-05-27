<template>
  <div id="app">
    <!-- Navbar -->
    <nav class="navbar">
      <div class="navbar-brand">Toko Online</div>
      <div class="navbar-nav">
        <a href="#" class="nav-item">Home</a>
        <a href="#" class="nav-item">Products</a>
        <a href="#" class="nav-item">About</a>
        <a href="#" class="nav-item">Contact</a>
      </div>
    </nav>

    <!-- Carousel -->
    <div class="carousel">
      <div class="carousel-item" v-for="(slide, index) in slides" :key="index">
        <img :src="slide.imgSrc" :alt="'Slide ' + (index + 1)">
        <div class="carousel-caption">
          <h5>{{ slide.caption }}</h5>
          <p>{{ slide.text }}</p>
        </div>
      </div>
    </div>

    <!-- Cards -->
    <div class="container">
      <div class="row">
        <div class="card" v-for="(product, index) in products" :key="index">
          <img :src="product.imgSrc" class="card-img-top" :alt="product.title">
          <div class="card-body">
            <h5 class="card-title">{{ product.title }}</h5>
            <p class="card-text">{{ product.description }}</p>
            <a href="#" class="btn btn-primary">Buy Now</a>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
      <p>&copy; 2024 Toko Online. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slides: [
        { imgSrc: '/img/slgt1.jpeg', caption: 'VND ring17', text: 'velg racing' },
        { imgSrc: '/img/slgt2.jpeg', caption: 'kaliper brembo', text: 'kaliper e di jogoooo' },
        { imgSrc: '/img/slgt3.jpeg', caption: 'biled ngabers', text: 'silau wak' }
      ],
      products: [
        { title: 'Product 1', description: 'Description of Product 1', imgSrc: '/img/p1.jpg' },
        { title: 'Product 2', description: 'Description of Product 2', imgSrc: '/img/p2.jpg' },
        { title: 'Product 3', description: 'Description of Product 3', imgSrc: '/img/p3.jpg' }
      ]
    }
  }
}
</script>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  padding-top: 70px;
  padding-bottom: 70px;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #333;
  color: white;
  display: flex;
  justify-content: space-between;
  padding: 1rem;
  z-index: 1000;
  box-sizing: border-box;
}

.navbar-brand {
  font-size: 1.5rem;
}

.navbar-nav {
  display: flex;
}

.nav-item {
  margin-left: 1rem;
  color: white;
  text-decoration: none;
}

.nav-item:hover {
  text-decoration: underline;
}

.carousel {
  display: flex;
  overflow-x: auto;
  scroll-behavior: smooth;
}

.carousel-item {
  min-width: 100%;
  position: relative;
}

.carousel-item img {
  width: 100%;
  height: auto;
}

.carousel-caption {
  position: absolute;
  bottom: 20px;
  left: 20px;
  color: white;
  background: rgba(0, 0, 0, 0.5);
  padding: 10px;
  border-radius: 5px;
}

.container {
  padding: 2rem 1rem;
}

.row {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

.card {
  width: 30%;
  margin-bottom: 2rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  overflow: hidden;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.card-img-top {
  width: 100%;
  height: auto;
}

.card-body {
  padding: 1rem;
}

.card-title {
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}

.card-text {
  margin-bottom: 1rem;
}

.btn-primary {
  background-color: #007bff;
  color: white;
  text-decoration: none;
  padding: 0.5rem 1rem;
  border-radius: 5px;
}

.btn-primary:hover {
  background-color: #0056b3;
}

.footer {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background-color: #333;
  color: white;
  text-align: center;
  padding: 1rem;
  box-sizing: border-box;
}
</style>
