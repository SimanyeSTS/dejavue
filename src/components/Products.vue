<template>
    <div class="page-container">
      <div v-if="products.length > 0" class="cards-container">
        <CardComp v-for="product in products" :key="product.id">
          <template v-slot:header>
            <h3>{{ product.name }}</h3>
          </template>
          <template v-slot:body>
            <p>ID: {{ product.id }}</p>
            <p>Price: {{ product.price }}</p>
            <p>Status: {{ product.status }}</p>
            <p>Description: {{ product.description }}</p>
          </template>
        </CardComp>
      </div>
      <div v-else class="spinner-border" role="status">
        <span class="sr-only">Loading...</span>
      </div>
    </div>
  </template>
  
  <script>
  import CardComp from '@/components/Card.vue';
  
  export default {
    name: 'ProductsComp',
    components: { CardComp },
    data() {
      return {
        products: [
          { id: 1, name: 'Laptop', price: 'R10000', status: 'Available', description: 'High-performance laptop' },
          { id: 2, name: 'Phone', price: 'R8500', status: 'Out of stock', description: 'Latest smartphone' },
          { id: 3, name: 'TV', price: 'R13000', status: 'Available', description: 'UFHD OLED Smart TV' }
        ]
      };
    }
  }
  </script>
  
  <style>
  .page-container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .cards-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
  }
  </style>
  