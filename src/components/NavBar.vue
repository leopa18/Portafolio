<template>
  <nav class="navbar">
    <div class="navbar-menu">
      <ul class="nav-list">
        <li v-for="nav in navegacion" :key="nav.id" class="nav-item">
          <a :href="nav.enlace">{{ nav.nombre }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue';
const navegacion = ref([
  { id: 1, nombre: 'Educación', enlace: '#educacion' },
  { id: 2, nombre: 'Experiencia', enlace: '#experiencia' },
  { id: 3, nombre: 'Proyectos', enlace: '#proyectos' },
  { id: 4, nombre: 'Habilidades', enlace: '#habilidades' },
  { id: 5, nombre: 'Intereses', enlace: '#intereses' }
]);
</script>

<style scoped>
.navbar {
  background-color: #8B5E3C; /* Marrón suave para la barra */
  color: #FFFFFF; /* Texto blanco */
  padding: 1rem; /* Espaciado aumentado */
  display: flex;
  justify-content: center; /* Centrar la navbar */
  border-bottom: 1px solid #6A3B28; /* Línea inferior color marrón más oscuro */
}

.nav-list {
  display: flex;
  list-style: none; /* Eliminar puntos de la lista */
  padding: 0; /* Eliminar padding */
  margin: 0; /* Eliminar margen */
}

.nav-item {
  margin: 0 1rem; /* Espacio entre elementos */
}

a {
  color: #FFFFFF; /* Texto blanco en los enlaces */
  text-decoration: none; /* Sin subrayado */
  transition: background-color 0.3s, color 0.3s; /* Suave transición */
  padding: 0.5rem 1rem; /* Espaciado interno */
  border-radius: 5px; /* Esquinas redondeadas */
}

a:hover {
  background-color: #6A3B28; /* Fondo marrón más oscuro al pasar el ratón */
  color: #FFFFFF; /* Color de texto blanco al pasar el ratón */
}
</style>
