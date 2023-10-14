<script setup>
const props = defineProps({
  product: Object,
});

const { title, description, category, price, image } = props.product;
</script>

<template>
  <!-- v-for="product in products" :key="products.id"  ind i div under-->
  <div class="card">
    <span class="rotate" v-if="category == 'electronics'">On Sale</span>
    <div :class="{ featured: category == 'electronics' }" class="product">
      <div class="product-image">
        <img :src="product.image" alt="Some bag" />
      </div>
      <div class="product-info">
        <header>
          <h3>{{ title }}</h3>
          <p class="price">{{ price }} kr</p>
          <p class="category">
            {{ category }}
          </p>
        </header>
        <p class="description">{{ description }}</p>
        <p
          :class="{
            red: props.product.rating.count <= 100,
            green: props.product.rating.count >= 300,
          }"
          class="stock"
        >
          {{ product.rating.count }}
        </p>
      </div>
    </div>
  </div>
  <!-- <h1>Bing Bong</h1> -->
</template>

<style></style>
