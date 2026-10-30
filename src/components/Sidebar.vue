<script setup>
</script>

<template>
  <aside class="sidebar">
    <h2 class="sidebar__title">Filters</h2>

    <section class="sidebar__block">
      <h3>Category</h3>
      <label><input type="checkbox" checked disabled /> Electronics</label>
      <label><input type="checkbox" disabled /> Clothing</label>
      <label><input type="checkbox" disabled /> Home</label>
    </section>

    <section class="sidebar__block">
      <h3>Price range</h3>
      <input type="range" min="0" max="1000" value="400" disabled />
      <p class="sidebar__hint">$0 – $400</p>
    </section>

    <section class="sidebar__block">
      <h3>Rating</h3>
      <label><input type="radio" name="rating" checked disabled /> 4★ & up</label>
      <label><input type="radio" name="rating" disabled /> 3★ & up</label>
      <label><input type="radio" name="rating" disabled /> 2★ & up</label>
    </section>
  </aside>
</template>

<style scoped>
.sidebar {
  width: 220px;
  min-width: 220px;
  padding: 1.25rem;
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
}

.sidebar__title {
  margin: 0 0 1rem;
  font-size: 1rem;
}

.sidebar__block {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin-bottom: 1.25rem;
}

.sidebar__block h3 {
  margin: 0;
  font-size: 0.875rem;
  color: #64748b;
}

.sidebar__block label {
  display: flex;
  align-items: center;
  gap: 0.4rem;
  font-size: 0.875rem;
  color: #334155;
}

.sidebar__block input[type='range'] {
  width: 100%;
}

.sidebar__hint {
  margin: 0;
  font-size: 0.8rem;
  color: #64748b;
}

@media (max-width: 700px) {
  .sidebar {
    width: 100%;
    min-width: 0;
  }
}
</style>
