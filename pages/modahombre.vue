<script setup>
import ProductList from '~/components/ProductList.vue'
import { items } from '~/public/corbatas/data.js'
</script>
<template>
  <div class="moda-page">
    <h1 class="corbatas-title">Moda Hombre</h1>
    <ProductList :items="items" />
  </div>
</template>

<style scoped>
.moda-page {
  min-height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
.corbatas-title {
  color: goldenrod;
  text-align: center;
  font-size: 2.2rem;
  margin: 2rem 0 1.5rem 0;
  letter-spacing: 2px;
  font-family: 'Playfair Display', serif;
}
</style>