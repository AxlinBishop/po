<template>
    <div v-if="visible" class="modal" @click="close">
        <div class="modal-content" @click.stop>
            <img :src="src" alt="Imagen en pantalla completa" />
        </div>
    </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

// Definición de las props
const props = defineProps({
    src: {
        type: String,
        required: true,
    },
    visible: {
        type: Boolean,
        required: true,
    },
});

// Definición de los eventos
const emit = defineEmits(['close']);

// Método para cerrar el modal
const close = () => {
    emit('close');
};
</script>

<style scoped>
.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
}

.modal-content {
    max-width: 90%;
    max-height: 90%;
}

.modal-content img {
    width: 100%;
    height: auto;
}
</style>