<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
const showMenu = ref(false)
const toggleMenu = () => {
  showMenu.value = !showMenu.value
}
const closeMenu = () => {
  showMenu.value = false
}

// Cerrar menú al hacer clic fuera
const handleClickOutside = (event) => {
  const nav = document.querySelector('nav')
  const btn = document.querySelector('.menu-btn')
  if (showMenu.value && nav && !nav.contains(event.target) && !btn.contains(event.target)) {
    closeMenu()
  }
}

onMounted(() => {
  document.addEventListener('click', handleClickOutside)
})
onBeforeUnmount(() => {
  document.removeEventListener('click', handleClickOutside)
})
</script>

<template>
  <div class="main-bg">
    <header class="header-custom">
      <div class="logo-container">
        <img src="/logo-bg.jpg" alt="Logo Quilino Reyes" class="logo-header" />
      </div>
      <button class="menu-btn" @click="toggleMenu" aria-label="Abrir menú">
        <span class="menu-icon"></span>
      </button>
      <nav :class="{ open: showMenu }">
        <NuxtLink to="/" @click="closeMenu">Inicio</NuxtLink>
        <NuxtLink to="/modahombre" @click="closeMenu">Moda Hombre</NuxtLink>
        <NuxtLink to="/modamujer" @click="closeMenu">Moda Mujer</NuxtLink>
        <NuxtLink to="/corbatashombre" @click="closeMenu">Corbatas Hombre</NuxtLink>
      </nav>
    </header>
    <main class="main-content">
      <NuxtPage />
    </main>
    <footer class="footer-custom">
      <p>&copy; 2025 Quilino Reyes · Moda Masculina</p>
    </footer>
  </div>
</template>

<style scoped>
.main-bg {
  min-height: 100vh;
  width: 100%;
  max-width: 100vw;
  background: #181818 url('/logo-bg.jpg') repeat center center fixed;
  background-size: 450px auto;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  overflow-x: hidden;
}
.main-content {
  flex: 1 1 auto;
  min-height: 1px;
  display: flex;
  flex-direction: column;
}
.header-custom {
  background: #181818;
  color: goldenrod;
  display: flex;
  flex-direction: row;
  align-items: center;
  border-bottom: 4px solid goldenrod;
  opacity: 0.97;
  height: 110px;
  min-height: 110px;
  justify-content: space-between;
  position: sticky;
  top: 0;
  z-index: 100;
  padding: 0 1rem;
}
.logo-container {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}
.logo-header {
  height: 100%;
  max-height: 110px;
  width: auto;
  object-fit: contain;
  display: block;
  border-radius: 10px;
  border: none;
}
.menu-btn {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  margin-left: 1rem;
  z-index: 200;
}
.menu-icon {
  width: 32px;
  height: 4px;
  background: goldenrod;
  display: block;
  position: relative;
  border-radius: 2px;
}
.menu-icon::before,
.menu-icon::after {
  content: '';
  position: absolute;
  left: 0;
  width: 32px;
  height: 4px;
  background: goldenrod;
  border-radius: 2px;
  transition: 0.3s;
}
.menu-icon::before {
  top: -10px;
}
.menu-icon::after {
  top: 10px;
}
nav {
  font-size: 1.3rem;
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  gap: 1.2rem;
  transition: all 0.3s;
}
nav a {
  color: goldenrod;
  text-decoration: none;
  transition: color 0.2s;
  font-size: 1.80rem;
  padding: 0.5rem 1rem;
  border-radius: 6px;
}
nav a:hover {
  color: #fff;
  background: rgba(218, 165, 32, 0.1);
}
.footer-custom {
  background: #181818;
  color: goldenrod;
  padding: 2rem 1rem 2rem 1rem;
  text-align: center;
  border-top: 4px solid goldenrod;
  margin-top: 0;
  opacity: 0.97;
  width: 100%;
  position: static;
}
body, html {
  background: #181818 !important;
  margin: 0 !important;
  padding: 0 !important;
  border: none !important;
  width: 100% !important;
  min-height: 100vh !important;
  box-sizing: border-box !important;
  overflow-x: hidden !important;
  /* position: fixed !important; */
  left: 0;
  top: 0;
}
body {
  background: #181818 !important;
  margin: 0 !important;
  padding: 0 !important;
  border: none !important;
  width: 100% !important;
  min-height: 100vh !important;
  box-sizing: border-box !important;
  overflow-x: hidden !important;
}
@media (max-width: 900px) {
  .header-custom {
    flex-wrap: wrap;
    height: auto;
    min-height: unset;
    padding: 0.5rem 0.5rem;
  }
  .menu-btn {
    display: block;
  }
  nav {
    position: absolute;
    top: 110px;
    left: 0;
    width: 100vw;
    min-height: 320px; /* Extiende el menú hacia abajo */
    background: #181818;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    gap: 0;
    padding: 0.5rem 0;
    display: none;
    border-bottom: 4px solid goldenrod;
    z-index: 150;
  }
  nav.open {
    display: flex;
  }
  nav a {
    font-size: 1.3rem;
    margin: 0;
    border-radius: 0;
    border-bottom: 1px solid goldenrod;
    border-right: none;
    border-left: none;
    border-top: none;
    width: 100%;
    padding: 0.8rem 1.2rem;
    text-align: left;
  }
  nav a:last-child {
    border-bottom: none;
  }
}
</style>
