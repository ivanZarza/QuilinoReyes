<template>
  <div>
    <h2>Temporada: {{ temporada }}</h2>
    <p>Aquí puedes mostrar las corbatas de la temporada seleccionada.</p>
  </div>
</template>

<script setup>
const route = useRoute()
const temporada = route.params.temporada
</script>
