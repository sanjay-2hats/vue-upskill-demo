<script setup>
    import Search from './header/search.vue';
    import Wishlist from './header/wishlist.vue';
    import Account from './header/account.vue';
    import Cart from './header/cart.vue';

    const props = defineProps({
      cart: {
        type: Number,
        required: true
      },
      total: {
        type: Number,
        required: true
      }
    })
</script>

<template>
  <header class="header">
    <a class="header__logo" href="#">Lumen</a>
    
    <Search />

    <nav class="header__actions" aria-label="Account">
      <Account />
      <Wishlist />
      <Cart :cart="cart" :total="total"/>
    </nav>
  </header>
</template>

<style scoped>
.header {
  display: flex;
  align-items: center;
  gap: 1rem;
  width: 100%;
  padding: 1rem 1.5rem;
  background: #fff;
  border-bottom: 1px solid #e5e7eb;
  position: sticky;
  top: 0;
  z-index: 100;
}

.header__logo {
  font-size: 1.25rem;
  font-weight: 700;
  color: #0f172a;
  text-decoration: none;
}

.header__actions {
  display: flex;
  gap: 0.35rem;
}

</style>
