<script setup>
    import { ref } from 'vue';
</script>

<template>
  <div class="header__actions">
    <button type="button">
    <svg viewBox="0 0 24 24" aria-hidden="true">
          <circle cx="12" cy="8" r="4" fill="none" stroke="currentColor" stroke-width="1.75" />
          <path
            d="M4 20c1.5-3.5 4.5-5 8-5s6.5 1.5 8 5"
            fill="none"
            stroke="currentColor"
            stroke-width="1.75"
            stroke-linejoin="round"
          />
        </svg>
    </button>
    <div class="header__account-info hidden">
        <h3>John Doe</h3>
        <p>john.doe@example.com</p>
    </div>
  </div>
</template>

<style scoped>

.header__actions button {
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

.header__actions svg {
  width: 1.2rem;
  height: 1.2rem;
}

.header__actions svg circle {
  fill: none;
  stroke: currentColor;
  stroke-width: 1.75;
}

.header__actions svg path {
  fill: none;
  stroke: currentColor;
  stroke-width: 1.75;
}

.hidden {
  display: none;
}
</style>