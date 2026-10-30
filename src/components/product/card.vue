<script setup>
  import { ref, onMounted } from 'vue';

  const props = defineProps({
    premium: {
      type: Boolean,
      required: true
    }
  });

  const products = ref([]);

  onMounted(async () => {
    const res = await fetch('https://dummyjson.com/products?limit=5');
    const data = await res.json();

    console.log(data);
    
    products.value = data.products.map(p => ({
      id: p.id,
      name: p.title,
      price: p.price,
      image: p.thumbnail,
      inventory: p.stock,
      onSale: p.discountPercentage > 10,
      variants: p.images.map((img, i) => ({ id: i, image: img }))
    }));
  });

  const emit = defineEmits(['add-to-cart']);

  const addCart = (product) => {
    emit('add-to-cart', product.price);
  }

  const updateImage = (product, variant) => {
    product.image = variant.image;
  }
</script>

<template>
  <article v-for="product in products" :key="product.id" class="card">
    <div class="image_container">
      <img :src="product.image" :alt="product.name" />
      <span v-if="product.inventory > 0 && product.inventory <= 5" class="badge almost_sold_out">Almost sold out!</span>
      <span v-else-if="product.inventory === 0" class="badge sold_out">Sold out!</span>
    </div>
      <div class="thumbnail">
        <div v-if="product.variants.length > 1" v-for="variant in product.variants" :key="variant.id" @mouseover="updateImage(product, variant)" class="thumbnail_item"
        :style="{ backgroundImage: `url(${variant.image})`, backgroundSize: 'cover' }">
        </div>
      </div>
      <h3>{{ product.name }}</h3>
      <p>${{ product.price }}</p>
      <p v-show="product.onSale">On sale</p>
      <p>shipping: <span v-if="premium">Free</span><span v-else>$120</span></p>
      <button type="button" @click="addCart(product)" :disabled="!product.inventory" :class="{ disabled: !product.inventory }">Add to cart</button>
  </article>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.image_container {
  width: 100%;
  height: 290px;
  position: relative;
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card h3 {
  font-size: 1.2rem;
}

.card p {
  font-size: 1rem;
}

.card button {
  font-size: 1rem;
  padding: 0.5rem 1rem;
  border: 1px solid #000;
  border-radius: 0.5rem;
  background-color: #fff;
  color: #000;
  cursor: pointer;
}

.card button:hover {
  background-color: #000;
  color: #fff;
}

.thumbnail {
  display: flex;
  gap: 1rem;
}

.thumbnail_item {
  width: 50px;
  height: 50px;
  cursor: pointer;
  border: 1px solid #000;
  border-radius: 50%;
}

.thumbnail_item img {
  object-fit: cover;
}

.disabled {
  opacity: 0.5;
  cursor: not-allowed !important;
}

.badge{
  position: absolute;
  top: 10px;
  left: 10px;
  z-index: 10;
  background-color: red;
  color: #fff;
  font-size: 0.8rem;
  font-weight: bold;
  padding: 0.5rem;
  border-radius: 0.5rem;
  border: 1px solid red;
}
.almost_sold_out{
  color: red;
  background-color: #fff;
  border: 1px solid red;
}
.sold_out{
  color: #fff;
  background-color: red;
  border: 1px solid red;
}
</style>