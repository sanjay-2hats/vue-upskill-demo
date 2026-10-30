<script setup>
  import { ref } from 'vue';
</script>

<template>
  <div class="header__wishlist">
    <button type="button">
    <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
      <path
        d="M12 20.5s-7.5-4.6-9.2-9.1C1.5 8.2 3.2 5 6.4 5c1.8 0 3.1 1 3.8 2.1C11 6 12.3 5 14.1 5c3.2 0 4.9 3.2 3.6 6.4-1.7 4.5-9.2 9.1-9.2 9.1z"
        stroke="currentColor"
        stroke-width="1.75"
        stroke-linejoin="round"
      />
    </svg>
    </button>
  </div>
</template>

<style scoped>
.header__wishlist button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 2.4rem;
  height: 2.4rem;
  padding: 0;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  background: #fff;
  color: #334155;
  cursor: pointer;
}

.header__wishlist svg {
  width: 1.2rem;
  height: 1.2rem;
}
</style>