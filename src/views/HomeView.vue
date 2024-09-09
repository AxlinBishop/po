<template>
    <div class="container_right">
        <div class="fondo_texto">
            <h2>¿Quién es Claudio Becerra?</h2>
            <p>Un apasionado desarrollador Front-End con un fuerte deseo de aprender y una
                dedicación a crear interfaces de usuario que sean tanto estéticamente atractivas como altamente funcionales.
            </p>
            <hr>
            <h2>Tecnologías</h2>
            <p>
                Mi experiencia se centra en el uso de tecnologías fundamentales como HTML, CSS y JavaScript, con las cuales
                diseño y desarrollo experiencias de usuario que no solo lucen bien, sino que también son intuitivas y
                fáciles de navegar.
            </p>
            <Tecnologias/>
            <hr>
            <p>
                Me considero un aprendiz perpetuo, siempre buscando nuevas oportunidades para expandir mis conocimientos y
                habilidades. Mi disposición para ayudar y colaborar me convierte en un miembro de equipo valioso, listo para
                enfrentar desafíos y contribuir al éxito de los proyectos en los que participo.
            </p>
            <p>
                Si estás interesado en saber más sobre mi trabajo o en explorar oportunidades de colaboración, te invito a
                que explores mi portafolio y te pongas en contacto conmigo a través de mi correo electrónico:
                claudioale094@gmail.com.
            </p>
            <p><b>¡Gracias por visitar mi portafolio!</b></p>
        </div>
    </div>
</template>

<script setup>
import Tecnologias from '@/components/Tecnologias.vue';
</script>

<style scoped>
.fondo_texto{
    padding: 2rem;
    background-color: rgba(199, 241, 227, 0.3);
}
h2{
    margin: 2rem 0;
}
p{
    margin: 2rem 0;
    font-weight: 600;
}
</style>