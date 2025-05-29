<script setup lang="ts">
import { ref } from 'vue';
import Envelope from './components/icons/Envelope.vue';
import Modal from './components/icons/Modal.vue';

const showModal = ref(false)

function showModalHandler() {
    showModal.value = true
    console.log("y");
    
}


function closeShowModalHandler() {
    showModal.value = false

}
</script>

<template>
    <main>
        <Envelope :showModal="showModalHandler" />
        <Modal :show-modal="showModal" :close-modal="closeShowModalHandler" />
    </main>
</template>