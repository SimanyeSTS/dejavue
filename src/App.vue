<template>
  <div id="app">
    <h1>My Friends</h1>
    <Friends />

    <h1>My Products</h1>
    <Products />
  </div>
</template>

<script>
import Friends from '@/components/Friends.vue';
import Products from '@/components/Products.vue';


export default {
  name: 'App',
  components: {
    Friends,
    Products
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
