<script setup>
import foto1 from "/src/assets/Codex5-1.jpg";
import foto2 from "/src/assets/Codex5-2.jpg";
import foto3 from "/src/assets/Codex5-3.jpg";
const proyectos = [
  {
    imgSrc: foto2,
    titulo: "E-commerce",
    descripcion: "Desarrollé una plataforma de comercio electrónico que aumentó las ventas en un 55% en su primer año, aplicando metodologías ágiles para optimizar el flujo de trabajo y mejorar la experiencia de compra.",
    youtubeLink: "https://youtube.com",
    githubLink: "https://github.com"
  },
  {
    imgSrc: foto1,
    titulo: "App de Gestión",
    descripcion: " Creé una aplicación de gestión de tareas que mejora la productividad en un 40% para los usuarios, implementando funciones intuitivas y opciones de organización personalizadas.",
    youtubeLink: "https://youtube.com",
    githubLink: "https://github.com"
  },
  {
    imgSrc: foto3,
    titulo: "App Delivery",
    descripcion: "Desarrollé un prototipo de aplicación de delivery, inspirado en plataformas como PedidosYa, Rappi y Glovo, con un enfoque en ofrecer una experiencia de usuario rápida y eficiente.",
    youtubeLink: "https://youtube.com",
    githubLink: "https://github.com"
  },
];
</script>

<template>
  <section id="proyectos">
    <div class="galeria">
      <div class="proyecto" v-for="(proyecto, index) in proyectos" :key="index">
        <img :src="proyecto.imgSrc" :alt="proyecto.titulo">
        <div class="proyecto-info">
          <h3>{{ proyecto.titulo }}</h3>
          <p>{{ proyecto.descripcion }}</p>
          <div class="proyecto-links">
            <a :href="proyecto.youtubeLink" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Proyecto</a>
            <a :href="proyecto.githubLink" class="github-link" target="_blank" rel="noopener noreferrer">Ver Código GitHub</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.galeria {
  width: 100%;
  height: auto; /* Cambiado para permitir el ajuste automático */
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  padding: 20px;
  justify-content: center;
  background: #F4E1D2; /* Fondo beige suave */
  border-radius: 15px; /* Bordes redondeados */
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3); /* Sombra suave */
}

.proyecto {
  display: flex;
  flex-direction: column;
  border: 2px solid rgba(255, 255, 255, 0.2); /* Borde sutil */
  overflow: hidden;
  background-color: #FAF3E0; /* Fondo pastel claro */
  max-width: 222px;
  flex: 1 1 300px;
  border-radius: 10px; /* Bordes redondeados */
  transition: transform 0.3s; /* Transición suave al pasar el mouse */
}

.proyecto:hover {
  transform: scale(1.05); /* Efecto de hover */
}

.proyecto img {
  width: 100%;
  height: auto;
  display: block;
  border-bottom: 2px solid rgba(255, 255, 255, 0.2); /* Línea sutil debajo de la imagen */
}

.proyecto-info {
  padding: 15px;
  text-align: center;
}

.proyecto-info h3 {
  margin: 10px 0;
  font-size: 1.3rem;
  color: #6F4F37; /* Marrón cálido */
}

.proyecto-info p {
  margin: 10px 0;
  font-size: 1em;
  color: #8e8e8e; /* Color gris para el texto */
}

.proyecto-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 10px;
}

.btn-ver-mas, .github-link {
  padding: 8px 12px; /* Ajuste de padding para botones */
  background-color: #6F4F37; /* Marrón cálido */
  color: #f5f5f5; /* Texto claro */
  border-radius: 5px; /* Bordes redondeados */
  text-decoration: none; /* Sin subrayado */
  transition: background-color 0.3s; /* Transición suave del fondo */
}

.btn-ver-mas:hover, .github-link:hover {
  background-color: #4B3621; /* Color marrón más oscuro al pasar el ratón */
}
</style>
