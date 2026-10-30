<script setup>
  import { ref } from 'vue';
</script>

<template>
    <div class="header__search">
      <input type="search" placeholder="Search…" aria-label="Search" />
    </div>
</template>

<style scoped>
.header__search {
  flex: 1;
}

.header__search input {
  width: 100%;
  max-width: 420px;
  padding: 0.55rem 0.85rem;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  font: inherit;
}
</style>