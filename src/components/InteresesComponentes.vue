<script>
import Fondolava from './FondoLava.vue'; // Importa el nuevo componente

export default {
  components: {
    Fondolava // Registra el componente
  },
  data() {
    return {
      intereses: [
        'Contribución en proyectos de código abierto: Colaboré en repositorios de código abierto en GitHub, mejorando funcionalidades de herramientas populares y fortaleciendo mis habilidades de desarrollo.',
        'Desarrollo de un videojuego independiente: Creé un videojuego desde cero, aplicando técnicas de diseño y programación para construir una experiencia interactiva y atractiva.',
        'Implementación de metodologías ágiles: Apliqué metodologías ágiles en mis proyectos personales, organizando sprints y mejorando la eficiencia de desarrollo de principio a fin.',
        'Mentoría y autoaprendizaje continuo: Me mantengo en constante aprendizaje, investigando y practicando con nuevas tecnologías para mejorar mis habilidades y mantenerme actualizado en el desarrollo de software.'
      ]
    }
  }
}
</script>

<template>
  <div class="intereses-contenedor">
    <!-- Fondo animado dentro del contenedor -->
    <Fondolava /> <!-- Utiliza el componente importado -->

    <!-- Lista de intereses -->
    <ul class="contenedor-lista">
      <li v-for="(interes, index) in intereses" :key="index" class="item">
        {{ interes }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
/* Contenedor principal de intereses */
.intereses-contenedor {
  position: relative;
  width: 100%; /* Asegura que ocupe el 100% de su contenedor padre */
  max-width: 100%; /* Ajusta el ancho máximo para que sea el 100% */
  margin: 2rem auto; /* Centrado con margen superior e inferior */
  padding: 2rem; /* Ajusta el padding para un diseño más limpio */
  border-radius: 10px; /* Esquinas redondeadas */
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2); /* Sombra sutil */
  background-color: transparent; /* Fondo transparente para que se vea la ola */
  z-index: 1; /* Asegura que el contenido se vea encima de la ola */
}

/* Fondo animado */
.fondo-animado {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1; /* Asegura que el fondo esté detrás del contenido */
  background-color: #F4A261; /* Fondo naranja suave para la ola */
}

/* Lista de intereses */
.contenedor-lista {
  list-style-type: none; /* Sin viñetas */
  padding: 0; /* Sin padding en la lista */
  margin: 0; /* Sin margen en la lista */
  color: rgb(255, 255, 255); /* Color de texto blanco */
  font-size: 1.4rem; /* Tamaño de fuente */
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8); /* Sombra de texto sutil */
}

.item {
  margin-bottom: 1rem; /* Espaciado entre elementos */
  line-height: 1.5; /* Mejora la legibilidad */
}
</style>
