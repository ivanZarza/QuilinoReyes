<script setup>
import ProductList from '~/components/ProductList.vue'
import { items5 } from '~/public/cofradia data/data.js'
</script>
<template>
  <div class="moda-page">
    <div class="corbatas-title-wrapper">
      <h1 class="corbatas-title">Moda Hombre</h1>
    </div>
    <ProductList :items="items5" imgBase="cofradiaImagen/" />
  </div>
</template>

<style scoped>
.moda-page {
  min-height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
.corbatas-title-wrapper {
  display: flex;
  justify-content: center;
  width: 100%;
  margin-top: 2rem;
  margin-bottom: 1.5rem;
}
.corbatas-title {
  color: goldenrod;
  text-align: center;
  font-size: 2.2rem;
  letter-spacing: 2px;
  font-family: 'Playfair Display', serif;
  backdrop-filter: blur(8px);
  background: rgba(0, 0, 0, 0.65);
  border-radius: 18px;
  padding: 1rem 2.5rem;
  display: inline-block;
  box-sizing: border-box;
  text-shadow: 0 2px 12px rgba(0,0,0,0.25);
}
</style>