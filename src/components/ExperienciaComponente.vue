<script setup>
import flecha from '/src/assets/addgente.svg';
import { ref } from 'vue';
const titulo = 'Desarrollador FullStack';
const fecha = 'Desde Abril 2024 / Diciembre 2024';
const experiencias = ref([
  { id: 1, src: flecha, parrafo: 'Contribución en proyectos de código abierto: Colaboré en repositorios de código abierto en GitHub, mejorando funcionalidades de herramientas populares y fortaleciendo mis habilidades de desarrollo.' },
  { id: 2, src: flecha, parrafo: 'Desarrollo de un videojuego independiente: Creé un videojuego desde cero, aplicando técnicas de diseño y programación para construir una experiencia interactiva y atractiva.' },
  { id: 3, src: flecha, parrafo: 'Implementación de metodologías ágiles: Apliqué metodologías ágiles en mis proyectos personales, organizando sprints y mejorando la eficiencia de desarrollo de principio a fin.' },
  { id: 4, src: flecha, parrafo: 'Mentoría y autoaprendizaje continuo: Me mantengo en constante aprendizaje, investigando y practicando con nuevas tecnologías para mejorar mis habilidades y mantenerme actualizado en el desarrollo de software.' },
  { id: 5, src: flecha, parrafo: 'Desarrollo de Software de código abierto: Contribuyo a proyectos en GitHub, colaborando con otros desarrolladores para mejorar herramientas y librerías populares.' },
]);
</script>

<template>
  <section id="experiencia">
    <div class="card">
      <h3 class="titulo">{{titulo}}</h3>
      <p class="fecha">{{fecha}}</p>
      <ul class="listado">
        <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
          <img class="imagen-svg" :src="experiencia.src" width="45rem" :alt="experiencia.parrafo">
          <p>{{ experiencia.parrafo }}</p>
        </li>
      </ul>
    </div>
  </section>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  padding: 2rem;
  background-color: #D1B19D; /* Marrón oscuro pastel */
  border-radius: 15px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3); /* Sombra más definida */
}

.titulo {
  font-size: 1.5rem;
  color: #3E2C1C; /* Marrón muy oscuro */
  text-align: center; /* Centrar título */
}

.fecha {
  font-size: 1rem;
  color: #5B4032; /* Marrón medio oscuro */
  margin-bottom: 1rem;
  text-align: center; /* Centrar fecha */
}

.listado {
  display: flex;
  flex-direction: column;
}

.item {
  align-items: flex-start; /* Alinear a la izquierda */
  display: flex;
  padding: 1rem;
  padding-left: 0; /* Eliminar padding izquierdo */
  border-bottom: 1px solid rgba(0, 0, 0, 0.1); /* Línea más oscura entre ítems */
}

.item:last-child {
  border-bottom: none; /* Quitar la línea del último ítem */
}

.imagen-svg {
  margin-right: 1rem; /* Espacio entre la imagen y el texto */
  filter: brightness(0) invert(1); /* Invertir colores de la imagen */
}

@media (min-width: 40rem) {
  ul {
    grid-template-columns: 1fr var(--line-w) 1fr;
  }
  ul::before {
    grid-column: 2;
  }
  ul li:nth-child(odd) {
    grid-column: 1;
  }
  ul li:nth-child(even) {
    grid-column: 3;
  }

  /* start second card */
  ul li:nth-child(2) {
    grid-row: 2/4;
  }
}

.credits {
  margin-top: 1rem;
  text-align: right;
}
.credits a {
  color: var(--color);
}
</style>
