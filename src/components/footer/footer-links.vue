<script setup>
  import { ref } from 'vue';
</script>

<template>
    <nav class="footer__links">
      <a href="#">About</a>
      <a href="#">Contact</a>
      <a href="#">Privacy</a>
    </nav>
</template>

<style scoped>
.footer__links {
  display: flex;
  gap: 1rem;
}
.footer__links a {
  color: #64748b;
  text-decoration: none;
}
</style>