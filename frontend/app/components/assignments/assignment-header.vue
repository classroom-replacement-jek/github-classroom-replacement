<template>
    <transition name="fade-above">
        <div v-if="mounted" class="h-[7vh] w-full mt-[15vh] flex justify-between items-center gap-6">
            <div class="flex h-full gap-4 items-center justify-start ">
                <button class="relative h-full! p-0 aspect-square rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white lg:text-4xl text-3xl flex justify-center items-center" @click="goBack">
                    <BackSquare :size="32" :color="'white'"/>
                </button>
                <button class="relative h-full! p-0 aspect-square rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white lg:text-4xl text-3xl flex justify-center items-center">
                    <Menu :size="32" :color="'white'" />
                </button>
                <h3 class="text-2xl inter text-white font-extrabold z-2">Assignment Name - Due 00/00/0000</h3>
            </div>
        </div>
    </transition>
</template>

<script setup lang="ts">
import { BackSquare, Menu, AddCircle } from 'reicon-vue';
const mounted = ref<boolean>(false)
onMounted((() => mounted.value = true))

function goBack() {
    const classId = useRoute().params.class_id
    console.log(classId)
    return navigateTo(`/classes/${classId}`)
}
</script>

<style scoped>
.fade-above-enter-from,
.fade-above-leave-to {
    opacity: 0;
    translate: 0 -60%
}

.fade-above-enter-to,
.fade-above-leave-from {
    opacity: 1
}

.fade-above-enter-active,
.fade-above-leave-active {
    transition: all 600ms ease-in-out
}
</style>