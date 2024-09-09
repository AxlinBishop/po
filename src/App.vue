<template>
<div class="wrapper">
  <div class="borde mainContainer"> <!-- un recuadro que encierre toda la vista que será el tamaño completo de la pantalla -->
    <div class="left">
      <NavMenu/>
    </div>
    <div class="right">
      <router-view v-slot="{ Component }">
        <transition name="fade"mode='out-in' >
          <component :is="Component"/>
        
        </transition>
      </router-view>
    </div>
  </div>
</div>

</template>

<script setup>
import NavMenu from './components/NavMenu.vue';


</script>

<style>
body{
  max-width: 1400px;
  margin: 0 auto;
  background-image:linear-gradient(rgba(255, 255, 255, 0.6), rgba(255, 255, 255, 0.9)), url('../public/bg.webp');
  background-size: cover;
  background-repeat: no-repeat;
  font-family: 'Roboto', sans-serif;
  background-attachment: fixed;
}
.mainContainer{ /* definir el tamaño de la vista */
  display: flex;
  width: calc(100vw - 3rem);
  height: calc(100vh - 4rem);
  margin: auto;
}
.borde{
  border: solid 2px black
}
.wrapper { /* contenedor padre para centrar el mainContainer */
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; 
}
h1{
  font-family: 'Sacramento', cursive;
}
.left{
  padding: 0 3rem 0 3rem;
  border-right: solid 2px black;
}
.right{
  margin: auto;
  align-items: right;
  width: 65%;
  height: 90%;
  overflow: auto;
  
}
/* barra de desplazamiento */
/* Estiliza la barra de desplazamiento (WebKit) */
.right::-webkit-scrollbar {
  width: 8px; /* Ancho de la barra de desplazamiento vertical */
  height: 8px; /* Altura de la barra de desplazamiento horizontal */
}

/* Estiliza la pista de la barra de desplazamiento (WebKit) */
.right::-webkit-scrollbar-track {
  background: rgba(199, 241, 227, 0.8); /* Color de fondo de la pista */
  border-radius: 10px; /* Bordes redondeados */
}

/* Estiliza el deslizador (WebKit) */
.right::-webkit-scrollbar-thumb {
  background: rgba(31, 92, 62, 0.7); /* Color del deslizador */
  border-radius: 10px; /* Bordes redondeados */
}

/* Cambia el color del deslizador al pasar el ratón (WebKit) */
.right::-webkit-scrollbar-thumb:hover {
  background: rgba(31, 92, 62, 1); /* Color del deslizador al pasar el ratón */
}

.container_right {
  margin: 2rem auto;
  width: 90%;

}
/* Animacion de transición */
.fade-enter-from, 
.fade-leave-to{ /* al comienzo y termino de la transición, va a ser transparente */
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active{
  transition: 0.5s ease-out;
}

/* media query */

@media (max-width: 700px) {
  .mainContainer{
    display: block;
  }
  .nav_menu{
    display: flex;
    flex-wrap: wrap;
  }
  .left{
    border-right: 0px;
  }
  body{
    background-attachment: fixed;
  }
  .mainContainer{ 
  width: calc(100vw - 3rem);
  height: 100%;
  margin: auto;
  }
  .wrapper { 
  height: 100%; 
  }
}



/* Otro MQ */
@media (max-width: 500px){
  .nav_menu{
    display: block;
  }
  .container_right {
    margin: 2rem 0.5rem;
    width: auto;
  }
  .right{
    width: 100%;
  }
}

@media (max-height: 570px) {
  .mainContainer {
    height: auto; /* Permite que el contenedor ajuste su altura según el contenido */
    overflow: auto; /* Mantiene el desbordamiento con barra de desplazamiento si es necesario */
  }
  
  .left {
    padding: 1rem; /* Reduce el padding para ajustarse a pantallas más pequeñas */
    border-bottom: solid 2px black; /* Asegura separación visual en lugar del borde derecho eliminado */
  }
  
  .right {
    width: 100%; /* Asegura que el contenido principal ocupe el ancho completo */
    height: auto; /* Permite que el contenido ajuste su altura según el tamaño disponible */
  }
  
  .container_right {
    margin: 1rem; /* Reduce el margen para ajustarse a pantallas más pequeñas */
    width: auto; /* Asegura que el contenedor use el ancho completo */
  }
  
  /* Ajuste adicional para fuentes y márgenes */
  h1 {
    font-size: 1.5rem; /* Reduce el tamaño de la fuente para adaptarse mejor a pantallas pequeñas */
  }
}
</style>
