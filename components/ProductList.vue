<template>
  <div class="product-list">
    <ProductCard
      v-for="item in items"
      :key="item.id"
      :nombre="item.nombre"
      :descripcion="item.descripcion"
      :precio="item.precio"
      :fotos="item.fotos"
    />
  </div>
</template>

<script setup>
import ProductCard from '~/components/ProductCard.vue'

defineProps({
  items: {
    type: Array,
    required: true
  }
})
</script>

<style scoped>
.product-list {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
  align-items: flex-start;
  padding: 2rem 0;
}
</style>
