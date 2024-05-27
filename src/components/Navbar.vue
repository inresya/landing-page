<template>
    <nav class="navbar">
      <div class="navbar-brand">My Store</div>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'Navbar',
  };
  </script>
  
  <style scoped>
  .navbar {
    position: fixed;
    top: 0;
    width: 100%;
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px 0;
    z-index: 1000;
  }
  .navbar-brand {
    font-size: 1.5rem;
  }
  </style>
  