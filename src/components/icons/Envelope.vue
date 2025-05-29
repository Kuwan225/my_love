<script setup>
import { ref } from 'vue';
import { FwbButton } from 'flowbite-vue';
import { LockClosedIcon, LockOpenIcon } from '@heroicons/vue/24/solid'

const props = defineProps(["showModal"])
const showMessage = ref(false)

function showMessageHandler() {
    showMessage.value = !showMessage.value
}

</script>

<template>
    <div class="flex justify-center items-center h-screen">
        <div class="container w-[250px] h-[200px] relative">
            <div class="sisi-atas top-[-113px]"></div>
            <div class="message w-[200px] h-[200px] bg-white absolute left-[25px] duration-800 p-2"
                :style="[showMessage ? 'top:-100px' : 'top:0px']">
                <div class="flex justify-between border-black border-b-1 p-2">
                    <div class="text-black text-[10px]">
                        <p>From : Marwan</p>
                        <p>To : Ariska</p>
                    </div>
                    <fwb-button gradient="blue" style=" padding: 2px 10px;" @click="props.showModal">open</fwb-button>
                </div>
                <div class="flex justify-center items-center h-[80%] flex-col gap-4">
                    <p class="text-black">I LOVE YOU MORE
                        <i :class="['fa-heart', 'fa-solid', liked ? 'text-red' : 'text-gray']" @click="liked = !liked"></i>
                    </p>
                </div>
            </div>
            <div class="w-[250px] h-[200px] relative overflow-hidden rounded-xl">
                <div class="sisi-kiri rotate-90 left-[-70px] bottom-[40px]"></div>
                <div class="sisi-kanan rotate-90 transform-[scaleY(-1)] right-[-70px] bottom-[40px]"></div>
                <div class="sisi-bawah bottom-[0px]"></div>
                <button
                    class="button-show-modal bg-[#BE3D2A] absolute bottom-8 left-[110px] rounded-full p-2 hover:bg-[#E78B48]"
                    @click="showMessageHandler">
                    <LockClosedIcon class="size-4 text-white" v-if="!showMessage" />
                    <LockOpenIcon class="size-4 text-white" v-if="showMessage" />
                </button>
            </div>
        </div>
    </div>
</template>

<style scoped>
.sisi-atas,
.sisi-kiri,
.sisi-kanan,
.sisi-bawah {
    width: 0;
    height: 0;
    border-left: 125px solid transparent;
    border-right: 125px solid transparent;
    border-bottom: 120px solid #F5C45E;
    position: absolute;
}
</style>