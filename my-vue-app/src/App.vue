<template>
  <div id="app">
    <nav class="navbar">
      <div class="container">
        <a class="navbar-brand" href="#">Toko Online</a>
        <div class="navbar-menu">
          <a class="navbar-item" href="#">Home</a>
          <a class="navbar-item" href="#">Products</a>
          <a class="navbar-item" href="#">Contact</a>
        </div>
      </div>
    </nav>
    <div class="carousel">
      <div class="carousel-item" v-for="(image, index) in images" :key="index">
        <img :src="image" :alt="'Slide ' + (index + 1)">
      </div>
    </div>
    <div class="cards-container">
      <div class="card" v-for="(product, index) in products" :key="index">
        <img :src="product.image" class="card-img" />
        <div class="card-body">
          <h5 class="card-title">{{ product.title }}</h5>
          <p class="card-text">{{ product.description }}</p>
          <a href="#" class="card-link">Learn More</a>
        </div>
      </div>
    </div>
    <footer class="footer">
      <div class="container">
        <p>&copy; 2024 Toko Online micko. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      images: [
        'k1.jpg',
        'download.jpg',
        'https://via.placeholder.com/800x300'
      ],
      products: [
        { image: 'k1.jpg', title: 'Product 1', description: 'baju' },
        { image: 'download.jpg', title: 'Product 2', description: 'kolor bermerek' },
        { image: 'download (1).jpg', title: 'Product 3', description: 'Description 3' }
      ]
    }
  }
}
</script>

<style>
.navbar {
  background-color: #333;
  color: #fff;
  padding: 1rem;
}
.navbar-brand {
  font-size: 1.5rem;
}
.navbar-menu {
  display: flex;
  gap: 1rem;
}
.navbar-item {
  color: #fff;
  text-decoration: none;
}

.carousel {
  display: flex;
  overflow-x: scroll;
  scroll-snap-type: x mandatory;
}
.carousel-item {
  min-width: 100%;
  scroll-snap-align: start;
}
.carousel-item img {
  width: 100%;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.card {
  border: 1px solid #ddd;
  border-radius: 5px;
  overflow: hidden;
  margin: 1rem;
  width: 200px; /* Adjusted width for better layout */
}
.card-img {
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
.card-link {
  color: #007bff;
  text-decoration: none;
}

.footer {
  background-color: #333;
  color: #fff;
  padding: 1rem 0;
  text-align: center;
}
</style>
