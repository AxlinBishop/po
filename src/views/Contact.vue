<template>
    <div class="container_right">
        <div class="text">
            <h3>¿Tienes alguna idea o proyecto en mente? ¡Házmelo saber! Completa el formulario abajo y charlemos sobre cómo podemos hacerlo realidad.</h3>
        </div>
        <hr>
        <div class="form-container">
            <form @submit.prevent="handleSubmit" class="contact-form">
                <h2>Contacto</h2>
                <div class="form-group">
                    <label for="name">Nombre</label>
                    <input v-model="form.name" type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Correo Electrónico</label>
                    <input v-model="form.email" type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="message">Mensaje</label>
                    <textarea v-model="form.message" id="message" name="message" rows="4" required></textarea>
                </div>
                <div class="btn-div">
                    <button class="btn" type="submit">Enviar</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import emailjs from 'emailjs-com';

const form = ref({
    name: '',
    email: '',
    message: ''
});

const handleSubmit = async () => {
    try {
        await emailjs.send('service_9malqwe', 'template_58kim19', {
            name: form.value.name,
            email: form.value.email,
            message: form.value.message
        }, 't4AaGgPRKnaz7Lvhp');
        alert('Correo electrónico enviado exitosamente');
        form.value.name = '';
        form.value.email = '';
        form.value.message = '';
    } catch (error) {
        alert('Error al enviar el correo electrónico');
    }
};
</script>

<style scoped>
.form-container {
    text-align: left;
    margin: 0 auto;
    width: 80%;
    padding: 1rem;
    background-color: rgba(199, 241, 227, 0.3);
}
.form-group{
    margin: 8px 0 8px 0;
}
h2{
    display: block;
    width: 80%;
    margin: 0 auto 1rem;
}
input,
textarea,
label {
    display: block;
    width: 80%;
    margin: auto;
}

/* estilo y animación del boton */
.btn-div {
    text-align: center; /* para centrar el botón, utilizo un div extra */
}
.btn {
    margin: 1rem;
    font-size: 16px;
    font-weight: 200;
    letter-spacing: 1px;
    padding: 13px 20px 13px;
    outline: 0;
    border: 1px solid black;
    cursor: pointer;
    position: relative;
    background-color: rgba(0, 0, 0, 0);
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
}
.btn:after {
    content: "";
    background-color: rgba(179, 229, 212, 1);
    width: 100%;
    z-index: -1;
    position: absolute;
    height: 100%;
    top: 7px;
    left: 7px;
    transition: 0.2s;
}
.btn:hover:after {
    top: 0px;
    left: 0px;
    background-color: rgb(94, 180, 151);
}

/* media query */
@media (min-width: 768px) {
    .btn {
        padding: 13px 50px 13px;
    }
}
</style>
