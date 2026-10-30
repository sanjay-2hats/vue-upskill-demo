<script setup>
  import Card from './product/card.vue';
  const props = defineProps({
    premium: {
      type: Boolean,
      required: true
    }
  });

  const emit = defineEmits(['add-to-cart']);

  const addToCart = (price) => {
    emit('add-to-cart', price);
  }
</script>

<template>
  <section class="listing">
    <div class="listing__top">
      <h1 class="listing__title">Shop</h1>
      <label class="listing__sort">
        Sort by
        <select disabled>
          <option>Newest</option>
          <option>Price: low to high</option>
          <option>Price: high to low</option>
        </select>
      </label>
    </div>

    <div class="listing__grid">
      <Card :premium="premium" @add-to-cart="addToCart"/>
    </div>

    <div class="listing__more">
      <button type="button">Load more</button>
    </div>
  </section>
</template>

<style scoped>
.listing {
  flex: 1;
  min-width: 0;
}

.listing__top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  margin-bottom: 1rem;
}

.listing__title {
  margin: 0;
  font-size: 1.5rem;
}

.listing__sort {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.875rem;
  color: #64748b;
}

.listing__sort select {
  padding: 0.4rem 0.6rem;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  font: inherit;
  background: #fff;
}

.listing__grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
}

.card {
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  overflow: hidden;
  padding-bottom: 1rem;
}

.card img {
  display: block;
  width: 100%;
  aspect-ratio: 4 / 3;
  object-fit: cover;
  background: #f1f5f9;
}

.card h3 {
  margin: 0.75rem 1rem 0.25rem;
  font-size: 1rem;
}

.card p {
  margin: 0 1rem 0.75rem;
  font-weight: 700;
}

.card button {
  margin: 0 1rem;
  padding: 0.45rem 0.75rem;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  background: #fff;
  font: inherit;
  font-size: 0.875rem;
  cursor: default;
}

.listing__more {
  display: flex;
  justify-content: center;
  margin-top: 1.5rem;
}

.listing__more button {
  padding: 0.65rem 1.25rem;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  background: #fff;
  font: inherit;
  font-weight: 600;
  cursor: default;
}

@media (max-width: 900px) {
  .listing__grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 560px) {
  .listing__grid {
    grid-template-columns: 1fr;
  }
}
</style>
