<template>
    <div v-for="(proyecto, index) in store.state.proyectos" :key="index">
        <div class="card_container">
            <div class="card_img" @click="showModal(proyecto.path)">
                <img :src="`${proyecto.path}.png`" alt="" >
            </div>

            <div class="card_body">
                <h2>Proyecto: {{ proyecto.nombre }}</h2>
                <p><b>Descripción:</b></p>
                <p>{{ proyecto.descripcion }}</p>
                <p><b>Detalles: </b></p>
                <p>{{ proyecto.detalles }}</p>
                <p><b>Tecnologías: </b></p>
                <div class="d-flex">
                    <div v-for="(tecnologia, index) in proyecto.tecnologias" :key="index">
                        <p class="tecnologia">{{ tecnologia }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!-- Modal para imagen -->
    <ModalImg :src="modalImageSrc" :visible="isModalVisible" @close="closeModal" />
</template>

<style scoped>
.d-flex {
    display: flex;
    flex-wrap: wrap;
}

.tecnologia {
    margin: 0 1rem;
    font-weight: 700;
}

.card_container {
    display: flex;
    margin: 0 auto;
    width: 90%;
    /*     height: 13rem; */
    margin: 1rem;
    padding: 0.5rem;
    background-color: rgba(199, 241, 227, 0.3);
    border: solid 2px rgba(31, 92, 62, 0.5);
    padding: 10px;
    border-width: 0.2em 0.4em 0 0.2em;
    border-radius: 0 2em 0 0;
}

.card_img {
    height: 15rem;
    aspect-ratio: 1 / 1;
    background-color: red;
    margin: auto 15px;
}

.card_img img {
    width: 100%;
    height: 100%;
    &:hover{
        filter: brightness(0.8);
    }
}

/* media query */
@media (max-width: 1000px) {
    .card_container {
        display: block;
    }

    .card_img {
        margin: auto;
    }
}
@media (max-width: 500px) {
    .card_img {
        height: 50vw;
        aspect-ratio: 1 / 1;
        background-color: red;
        margin: auto 15px;
    }
    .card_container {
        width: 70%;
        margin: 1rem 2rem;
        padding: 0.5rem;
        border-width: 0.2em 0.4em 0 0.2em;
        border-radius: 0 2em 0 0;
    }
}
</style>


<script setup>
import { ref } from 'vue';
import { useStore } from 'vuex';
import ModalImg from './ModalImg.vue';

const store = useStore();

const isModalVisible = ref(false);
const modalImageSrc = ref('');

const showModal = (path) => {
    modalImageSrc.value = `/${path}.png`;
    isModalVisible.value = true;
};

const closeModal = () => {
    isModalVisible.value = false;
};
</script>