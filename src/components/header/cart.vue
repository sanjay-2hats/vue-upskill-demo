<script setup>
    import { ref } from 'vue';
    

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
  <div class="header__cart">
    <button type="button">
    <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
      <path
        d="M3 4h1.5l1.2 2.4L8 14h9.5l2-8H7"
        stroke="currentColor"
        stroke-width="1.75"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <circle cx="9" cy="19" r="1.5" fill="currentColor" />
      <circle cx="17" cy="19" r="1.5" fill="currentColor" />
    </svg>
    </button>
    <span v-if="cart > 0" class="header__cart-count">{{ cart }}</span>
    <span v-if="cart > 0" class="header__cart-price">{{ total }}</span>
  </div>
</template> 

<style scoped>
.header__cart{
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}
.header__cart button {
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

.header__cart svg {
  width: 1.2rem;
  height: 1.2rem;
}
.header__cart-count {
  position: absolute;
  top: -8px;
  right: -8px;
  background: #ff0000;
  color: #fff;
  border-radius: 50%;
  padding: 4px 6px;
  font-size: 10px;
  font-weight: 600;
  line-height: 1;
}
</style>