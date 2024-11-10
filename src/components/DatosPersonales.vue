<script setup>
const title = "Leonel Palominos"
const descripcion = "Tecnico Universitario en Programación - UTN"
const residencia = "San Rafael, Mendoza Argentina"
const presentacion = "Bienvenido a mi portafolio. Soy desarrollador web y me especializo en el desarrollo de soluciones web y móviles. Explora mis proyectos para conocer más sobre mi trabajo."
const redesSociales = [
    {id:1, name:"Linkedin", src:'/src/assets/linkedin_icon.svg',url:'https://www.linkedin.com/in/leonelpalominos/'},
    {id:1, name:"Instagram", src:'/src/assets/instagram_icon.svg',url:'https://instagram.com/'},
    {id:1, name:"Github", src:'/src/assets/github_icon.svg',url:'https://github.com/leopa18'},
    {id:1, name:"CurriculumVitae", src:'/src/assets/cv_icon.svg',url:''},
];
const telefono = "+54 2994618267"
</script>

<template>
<section class="datos-personales">
    <div class="card">
        <h1>{{ title }}</h1>
        <h2>{{ descripcion }}</h2>
        <p>{{ presentacion }}</p>
        <ul class="container-lista">
            <li v-for="red in redesSociales" :key="red.id">
                <a href="red.url"><img class="icon-redsocial" :src="red.src" width="35rem" :alt="red.name"></a>
            </li>
        </ul>
        <h3>Mi telefono personal: {{ telefono }}</h3>
        <h4>{{ residencia }}</h4>
    </div>
</section>
</template>

<style scoped>
h1 {
    font-size: 2.5rem;
}

p {
    font-size: 1.2rem;
    font-weight: 600;
    margin-bottom: 1rem;
}

.card {
    background-color: #d7ccc8; /* Fondo marrón pastel */
    border-radius: 10px;
    padding: 10px;
    margin: 10px;
    text-align: center;
    color: #3e2723; /* Texto marrón oscuro */
}

.container-lista {
    display: flex;
    justify-content: center;
    list-style: none;
    padding: 0;
    margin: 0;
    text-align: center;
}

.icon-redsocial {
    align-items: center;
    background-color: #f5f5f5; /* Fondo gris claro */
    border-radius: 50%;
    padding: 2px;
    margin: 5px;
    box-shadow: 0 0 5px rgba(121, 85, 72, 0.7); /* Sombra marrón pastel */
}

.icon-redsocial:hover {
    background-color: #8d6e63; /* Cambio a un marrón más oscuro */
    box-shadow: 0 0 5px rgba(121, 85, 72, 0.8);
}

h3 {
    font-size: 1.2rem;
    font-weight: 600;
}
</style>
