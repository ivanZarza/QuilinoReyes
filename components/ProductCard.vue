<template>
  <div class="product-card">
    <div class="product-image" @click.stop="openGallery">
      <img :src="`${imgBase}${fotos[0]}`" :alt="nombre" />
    </div>
    <div class="product-info">
<!--       <h2>{{ nombre }}</h2> -->
      <p class="desc">{{ descripcion }}</p>
      <p class="precio">{{ precio }}</p>
    </div>
    <div v-if="showGallery" class="modal-overlay" @click.self="closeGallery">
      <div class="modal-gallery">
        <button class="close-btn" @click="closeGallery">&times;</button>
        <div class="gallery-main">
          <img :src="`${imgBase}${fotos[galleryIndex]}`" :alt="nombre" />
        </div>
        <div class="gallery-thumbs">
          <img
            v-for="(foto, idx) in fotos"
            :key="idx"
            :src="`${imgBase}${foto}`"
            :alt="nombre + ' miniatura ' + idx"
            :class="{active: idx === galleryIndex}"
            @click.stop="galleryIndex = idx"
          />
        </div>
        <button class="nav-btn left" @click.stop="prevImage">&#8592;</button>
        <button class="nav-btn right" @click.stop="nextImage">&#8594;</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const props = defineProps({
  nombre: String,
  descripcion: String,
  precio: String,
  fotos: Array,
  imgBase: {
    type: String,
    default: ''
  }
})
const showGallery = ref(false)
const galleryIndex = ref(0)
function openGallery() {
  showGallery.value = true
  galleryIndex.value = 0
}
function closeGallery() {
  showGallery.value = false
}
function prevImage() {
  galleryIndex.value = (galleryIndex.value - 1 + props.fotos.length) % props.fotos.length
}
function nextImage() {
  galleryIndex.value = (galleryIndex.value + 1) % props.fotos.length
}
</script>

<style scoped>
.product-card {
  width: 320px;
  min-height: 540px;
  max-height: 540px;
  background: rgba(26,26,26,0.98);
  border: 2px solid goldenrod;
  border-radius: 18px;
  box-shadow: 0 2px 16px 0 rgba(0,0,0,0.18);
  color: #fff;
  margin: 1.5rem auto;
  cursor: pointer;
  transition: box-shadow 0.2s, border 0.2s;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
}
.product-card:hover {
  box-shadow: 0 6px 32px 0 rgba(218,165,32,0.18);
  border-color: #fff;
}
.product-image {
  width: 100%;
  height: 370px;
  background: #111;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  cursor: zoom-in;
}
.product-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-bottom: 1px solid goldenrod;
}
.product-info {
  padding: 1.2rem 1rem 1.5rem 1rem;
  text-align: center;
}
.product-info h2 {
  color: goldenrod;
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
}
.product-info .desc {
  font-size: 1rem;
  color: #eee;
  margin-bottom: 0.7rem;
}
.product-info .precio {
  color: #fff;
  font-size: 1.1rem;
  font-weight: bold;
  background: goldenrod;
  border-radius: 8px;
  padding: 0.3rem 1rem;
  display: inline-block;
  margin-top: 0.5rem;
}
.modal-overlay {
  position: fixed;
  top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(0,0,0,0.85);
  z-index: 9999;
  display: flex;
  align-items: center;
  justify-content: center;
}
.modal-gallery {
  background: #222;
  border: 2px solid goldenrod;
  border-radius: 18px;
  padding: 2rem 2rem 1.2rem 2rem;
  box-shadow: none;
  position: relative;
  max-width: 90vw;
  max-height: 90vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.close-btn {
  position: absolute;
  top: 12px;
  right: 18px;
  left: auto;
  background: goldenrod;         
  border: 2px solid #fff;        
  color: #fff;               
  font-size: 2.2rem;
  cursor: pointer;
  z-index: 2;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 8px 0 rgba(0,0,0,0.10);
  transition: background 0.2s, color 0.2s, border 0.2s;
  padding: 0;
}
.close-btn:hover {
  background: #fff;                
  color: goldenrod;              
  border: 2px solid goldenrod;    
}
.gallery-main {
  width: 60vw;
  max-width: 500px;
  max-height: 70vh;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.2rem;
  /* Asegura que el contenedor no tenga padding extra */
  padding: 0;
  overflow: hidden;
}
.gallery-main img {
  width: 100%;
  height: 100%;
  max-width: 100%;
  max-height: 100%;
  border-radius: 12px;
  border: 2px solid goldenrod;
  background: #111;
  object-fit: cover; /* Cambiado a cover para llenar el contenedor */
  display: block;
}
.gallery-thumbs {
  display: flex;
  gap: 0.7rem;
  margin-bottom: 0.7rem;
  justify-content: center;
}
.gallery-thumbs img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  border-radius: 8px;
  border: 2px solid transparent;
  cursor: pointer;
  transition: border 0.2s;
}
.gallery-thumbs img.active {
  border: 2px solid goldenrod;
}
.nav-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: goldenrod;         /* Fondo dorado por defecto */
  border: 2px solid #fff;        /* Borde blanco por defecto */
  color: #fff;                   /* Flecha blanca por defecto */
  font-size: 2rem;
  border-radius: 8px;
  width: 54px;
  height: 40px;
  cursor: pointer;
  z-index: 2;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 8px 0 rgba(0,0,0,0.10);
  transition: background 0.2s, color 0.2s, border 0.2s;
  padding: 0;
  line-height: 1;
  padding-bottom: 12px;
}
.nav-btn:hover {
  background: #fff;              /* Fondo blanco al hacer hover */
  color: goldenrod;              /* Flecha dorada al hacer hover */
  border: 2px solid goldenrod;   /* Borde dorado al hacer hover */
}
.nav-btn.left {
  left: 10px;
}
.nav-btn.right {
  right: 10px;
}
@media (max-width: 600px) {
  .gallery-main {
    width: 90vw;
    max-width: 95vw;
  }
  .modal-gallery {
    padding: 0.7rem 0.2rem 0.7rem 0.2rem;
  }
}
</style>
