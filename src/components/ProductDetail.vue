<!-- src/components/ProductDetail.vue -->
<template>
    <div class="product-detail">
      <h4>{{ product.name }}</h4>
      <p>{{ product.description }}</p>
      <p>Harga: {{ product.price }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['product']
  };
  </script>
  
  <style scoped>
  .product-detail {
    border: 1px solid #ddd;
    padding: 10px;
    margin: 10px 0;
  }
  </style>
  