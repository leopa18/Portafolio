<script setup> 
import { ref } from 'vue';

const fechaColor = ref([
  { color: "#d7ccc8" },
  { color: "#8d6e63" },
  { color: "#6d4c41" },
  { color: "#bc8a5b" },
  { color: "#a1887f" }
]);

const educacion = ref([
  { fecha: '2024', title: 'Tecnicatura Universitaria en Programación', descripcion: 'Incumbencias Profesionales: Desarrollo y mantenimiento de sistemas, optimización de bases de datos, y programación en múltiples lenguajes.' },
  { fecha: '2023', title: 'Desarrollador Frontend', descripcion: 'Trabajé en Innovatech, desarrollando y optimizando interfaces interactivas con tecnologías como React, Vue.js y Sass.' },
  { fecha: '2022', title: 'Internship en Desarrollo de Aplicaciones Móviles', descripcion: 'Realicé una pasantía en Mobile Solutions, colaborando en el diseño y la implementación de aplicaciones móviles con tecnologías como Flutter y Kotlin.' },
  { fecha: '2021', title: 'Proyecto Personal - Plataforma de E-commerce', descripcion: 'Desarrollé una plataforma de comercio electrónico que permite gestionar productos, pagos y usuarios usando tecnologías como HTML, CSS y PHP.' },
  { fecha: '2020', title: 'Curso de Programación Orientada a Objetos', descripcion: 'Completé un curso especializado en programación orientada a objetos, adquiriendo conocimientos en Java y prácticas de diseño modular.' }
]);
</script>

<template>
  <section id="educacion">
  <ul>
    <li v-for="(item, index) in educacion" :key="index" :style="{ '--accent-color': fechaColor[index].color }">
      <div class="date">{{ item.fecha }}</div>
      <div class="title">{{ item.title }}</div>
      <div class="descr">{{ item.descripcion }}</div>
    </li>
  </ul>
  <div class="credits"><a target="_blank" href="https://www.freepik.com/free-vector/infographic-template-with-yearly-info_1252895.htm"></a></div>
</section>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap");

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  --color: rgba(78, 54, 33); /* Marrón oscuro */
  --bgColor: #f5f5f5; /* Gris claro */
  min-height: 100vh;
  display: grid;
  align-content: center;
  gap: 2rem;
  padding: 2rem;
  font-family: "Poppins", sans-serif;
  color: var(--color);
  background: var(--bgColor);
}

h1 {
  text-align: center;
  color: #5d4037; /* Marrón cálido */
}

ul {
  --col-gap: 2rem;
  --row-gap: 2rem;
  --line-w: 0.25rem;
  display: grid;
  grid-template-columns: var(--line-w) 1fr;
  grid-auto-columns: max-content;
  column-gap: var(--col-gap);
  list-style: none;
  width: min(60rem, 90%);
  margin-inline: auto;
}

ul::before {
  content: "";
  grid-column: 1;
  grid-row: 1 / span 20;
  background: #bc8a5b; /* Marrón cálido */
  border-radius: calc(var(--line-w) / 2);
}

ul li:not(:last-child) {
  margin-bottom: var(--row-gap);
}

ul li {
  grid-column: 2;
  --inlineP: 1.5rem;
  margin-inline: var(--inlineP);
  grid-row: span 2;
  display: grid;
  grid-template-rows: min-content min-content min-content;
}

ul li .date {
  --dateH: 3rem;
  height: var(--dateH);
  margin-inline: calc(var(--inlineP) * -1);
  text-align: center;
  background-color: var(--accent-color);
  color: white;
  font-size: 1.25rem;
  font-weight: 700;
  display: grid;
  place-content: center;
  position: relative;
  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
}

ul li .date::before {
  content: "";
  width: var(--inlineP);
  aspect-ratio: 1;
  background: var(--accent-color);
  background-image: linear-gradient(rgba(0, 0, 0, 0.2) 100%, transparent);
  position: absolute;
  top: 100%;
  clip-path: polygon(0 0, 100% 0, 0 100%);
  right: 0;
}

ul li .date::after {
  content: "";
  position: absolute;
  width: 2rem;
  aspect-ratio: 1;
  background: var(--bgColor);
  border: 0.3rem solid var(--accent-color);
  border-radius: 50%;
  top: 50%;
  transform: translate(50%, -50%);
  right: calc(100% + var(--col-gap) + var(--line-w) / 2);
}

ul li .title,
ul li .descr {
  background: var(--bgColor);
  position: relative;
  padding-inline: 1.5rem;
}

ul li .title {
  overflow: hidden;
  padding-block-start: 1.5rem;
  padding-block-end: 1rem;
  font-weight: 500;
}

ul li .descr {
  padding-block-end: 1.5rem;
  font-weight: 300;
}

ul li .title::before,
ul li .descr::before {
  content: "";
  position: absolute;
  width: 90%;
  height: 0.5rem;
  background: rgba(0, 0, 0, 0.5);
  left: 50%;
  border-radius: 50%;
  filter: blur(4px);
  transform: translate(-50%, 50%);
}

ul li .title::before {
  bottom: calc(100% + 0.125rem);
}

ul li .descr::before {
  z-index: -1;
  bottom: 0.25rem;
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

  ul li:nth-child(2) {
    grid-row: 2/4;
  }

  ul li:nth-child(odd) .date::before {
    clip-path: polygon(0 0, 100% 0, 100% 100%);
    left: 0;
  }

  ul li:nth-child(odd) .date::after {
    transform: translate(-50%, -50%);
    left: calc(100% + var(--col-gap) + var(--line-w) / 2);
  }
  ul li:nth-child(odd) .date {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
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
