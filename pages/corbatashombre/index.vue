<script setup>
import ProductList from '~/components/ProductList.vue'
import { items } from '~/public/corbatas/data.js'
import { ref } from 'vue'

const primaveraVerano = [...items].reverse(); // Orden invertido
const otonoInvierno = [...items]; // Orden original

const temporadas = [
  { nombre: 'Primavera-Verano', items: primaveraVerano },
  { nombre: 'Otoño-Invierno', items: otonoInvierno }
]
const temporadaSeleccionada = ref(temporadas[0])
</script>
<template>
  <div>
    <h1 class="corbatas-title">Corbatas Hombre</h1>
    <div class="temporadas-tabs">
      <button
        v-for="temp in temporadas"
        :key="temp.nombre"
        :class="['tab-btn', { active: temp.nombre === temporadaSeleccionada.nombre }]"
        @click="temporadaSeleccionada = temp"
      >
        {{ temp.nombre }}
      </button>
    </div>
    <div class="product-list-wrapper">
      <ProductList :items="temporadaSeleccionada.items" />
    </div>
  </div>
</template>

<style scoped>
.corbatas-title {
  color: goldenrod;
  text-align: center;
  font-size: 2.2rem;
  margin: 2rem 0 1.5rem 0;
  letter-spacing: 2px;
  font-family: 'Playfair Display', serif;
}
.temporadas-tabs {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}
.tab-btn {
  background: none;
  border: 2px solid goldenrod;
  color: goldenrod;
  font-size: 1.1rem;
  padding: 0.5rem 1.5rem;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.2s, color 0.2s;
  margin-bottom: 0.5rem;
}
.tab-btn.active, .tab-btn:hover {
  background: goldenrod;
  color: #181818;
}
.product-list-wrapper {
  width: 92vw;
  max-width: 1200px;
  margin: 0 auto 2rem auto;
}

@media (max-width: 700px) {
  .corbatas-title {
    font-size: 1.4rem;
    margin: 1.2rem 0 1rem 0;
  }
  .temporadas-tabs {
    gap: 0.7rem;
    margin-bottom: 1.2rem;
  }
  .tab-btn {
    font-size: 1rem;
    padding: 0.4rem 1rem;
  }
}
@media (max-width: 450px) {
  .corbatas-title {
    font-size: 1.1rem;
    margin: 0.8rem 0 0.7rem 0;
  }
  .temporadas-tabs {
    flex-direction: column;
    align-items: center;
    gap: 0.4rem;
  }
  .tab-btn {
    width: 90vw;
    max-width: 260px;
    font-size: 0.98rem;
    padding: 0.4rem 0.5rem;
  }
}
@media (max-width: 600px) {
  .product-list-wrapper {
    width: 90vw;
    max-width: 95vw;
    padding-left: 5vw;
    padding-right: 5vw;
    box-sizing: border-box;
  }
}
</style>
