<script setup>
import Header from './components/header.vue'
import Sidebar from './components/Sidebar.vue'
import ProductListing from './components/ProductListing.vue'
import Footer from './components/Footer.vue'

import { ref } from 'vue';

const cart = ref(0);
const total = ref(0);
const premium = ref(true);

const addToCart = (price) => {
  total.value = price + total.value;
  cart.value++;
  console.log(total.value);
}
</script>

<template>
  <div class="app">
    <Header :cart="cart" :total="total"/>

    <main class="app__content">
      <Sidebar />
      <ProductListing  :premium="premium" @add-to-cart="addToCart"/>
    </main>

    <Footer />
  </div>
</template>

<style scoped>
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background: #f8fafc;
}

.app__content {
  display: flex;
  gap: 1.25rem;
  flex: 1;
  width: 100%;
  padding: 1.25rem 1.5rem;
}

@media (max-width: 700px) {
  .app__content {
    flex-direction: column;
  }
}
</style>
