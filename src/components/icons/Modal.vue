<script setup>
import { FwbModal } from 'flowbite-vue';


const props = defineProps(["showModal", "closeModal"])

</script>


<template>
    <fwb-modal v-show="props.showModal" @close="props.closeModal" size="xl">
        <template #header>
            <div class="flex items-center text-lg">
                DARI KUWANNN UNTUK IKAAA 10.000 KATA "i love you"
            </div>
        </template>
        <template #body>
            <div style="display: flex; flex-wrap: wrap; gap: 10px;">
                <p v-for="n in 100000" :key="n" class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
                    i love you
                </p>
            </div>
        </template>
    </fwb-modal>
</template>
