<template>
    <div class="container_nombre">
        <h1>Claudio Becerra</h1>
        <h3>Desarrollador Front-End</h3>
    </div>
    <hr>
    <nav> <!-- ordenarlo como un aside -->
        <div class="nav_menu">
            <router-link to="/">Inicio</router-link>
            <router-link to="/projects">Proyectos</router-link>
            <router-link to="/contact">Contacto</router-link>
        </div>
    </nav>
    <hr>
</template>

<style scoped>
body {
    width: 100%;
}

.nav_menu {
    font-size: large;
    text-align: center;
    padding: 0;
}

a {
    /* estilo de los links */
    margin: 0.5rem 0;
    display: block;
    text-decoration: none;
    color: black;
}

a:hover{
    color: rgb(49, 172, 111);
}
a.router-link-active {
    border-bottom: solid 2px rgb(49, 172, 111);
}

.container_nombre {
    flex: 1;
    margin: 5rem 0 3rem 0;
    text-align: center;
}
.container_nombre h1{
    font-size: 4rem;
}

/* media queryes */
/*  estilo para pantallas menores a 700px */
@media (max-width: 700px) {
    a {
        margin: 0 0.3rem;;
    }
    nav{
        display: flex;
        justify-content: center;
    }
}
</style>