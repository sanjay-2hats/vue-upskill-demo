<script setup>
  import FooterLinks from './footer/footer-links.vue';
</script>

<template>
  <footer class="footer">
    <p>© 2026 Lumen. Sample Vue shop page.</p>
    <FooterLinks />
  </footer>
</template>

<style scoped>
.footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 1.25rem 1.5rem;
  background: #fff;
  border-top: 1px solid #e5e7eb;
  color: #64748b;
  font-size: 0.875rem;
}

.footer p {
  margin: 0;
}

.footer__links {
  display: flex;
  gap: 1rem;
}
</style>
