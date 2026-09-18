<template>
    <div>
        <transition name="fade-above">
            <div v-if="mounted" class="fixed top-0 h-[7vh] bg-none flex m-[2vw] items-center justify-between w-[96vw]">
                <div class="flex justify-start items-center gap-6">
                    <div class="h-[7vh] rounded-full bg-white aspect-square">
    
                    </div>
                    <h3 class="inter font-extrabold text-3xl text-white max-w-[50vw]">username</h3>
                </div>
            <button @click="logOut" class="rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] hover:-translate-y-0.5 active:translate-y-1 ease-in-out inter font-bold text-white lg:text-2xl text-xl items-center max-h-full px-12 py-6 justify-around flex gap-4">
                <ArrowDoorOut :size="24" />
                Log Out</button>
            </div>
        </transition>
        <slot></slot>
    </div>
</template>

<script setup lang="ts">
import { ArrowDoorOut } from 'reicon-vue';

const mounted = ref<boolean>(false)
onMounted((() => mounted.value = true))

function logOut() {
    return navigateTo('/')
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
    transition: all 300ms ease-in-out
}
</style>