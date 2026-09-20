<template>
    <div>
        <transition name="fade-above">
            <div v-if="mounted" class="fixed top-0 h-[7vh] bg-none flex m-[2vw] items-center justify-between w-[96vw]">
                <div class="flex justify-start items-center gap-6 h-full w-[60%]">
                    <div class="h-[7vh] rounded-full bg-white aspect-square">
    
                    </div>
                    <h3 class="inter font-extrabold text-3xl text-white max-w-[50vw] select-none hover:text-cyan-200 active:text-cyan-400 transition-colors ease-in-out duration-300"
                    @click="changingDisplayName = true">
                    username</h3>
                    <transition name="fade" appear mode="out-in">
                        <div  v-if="changingDisplayName" class="h-fit w-fit flex items-center gap-2">
                            <input type="text"
                            class="bg-black/50 focus:bg-black transition-colors ease-in-out duration-150 w-full h-[80%] rounded-lg focus:outline-none placeholder-cyan-300/60 text-white inter font-bold text-lg px-2 py-2" placeholder="Change Display Name"
                            >
                            <button class="relative p-2 aspect-square rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white flex justify-center items-center" @click="changingDisplayName = false">
                                <X :size="24" weight="Filled" :color="'white'"/>
                            </button>
                            <button class="relative p-2 aspect-square rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white flex justify-center items-center" @click="">
                                <Check :size="24" weight="Filled" :color="'white'"/>
                            </button>
                        </div>
                    </transition>
                </div>
            <button @click="logOut" class="rounded-full bg-[#22c9e3] shadow-lg hover:shadow-xl active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] hover:-translate-y-0.5 active:translate-y-1 ease-in-out inter font-bold text-white lg:text-2xl text-xl items-center max-h-full px-12 py-6 justify-around flex gap-4">
                <ArrowDoorOut :color="'white'" :size="24" />
                Log Out</button>
            </div>
        </transition>
        <slot></slot>
    </div>
</template>

<script setup lang="ts">
import { ArrowDoorOut, X, Check } from 'reicon-vue';

const mounted = ref<boolean>(false)
const changingDisplayName = ref<boolean>(false)
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
    transition: all 600ms ease-in-out
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity 400ms ease-in-out;
}

.fade-enter-to,
.fade-leave-from {
    opacity: 1;
}
</style>