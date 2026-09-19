<template>
    <div class="bg-[#262D35] min-h-dvh w-[vw] py-[2%] px-[5%] flex flex-col justify-around gap-[10vh]">
        <transition name="fade-above">
            <h1 v-if="mounted" class="text-[#B5FFF9] lg:text-[120px] md:text-[100px] text-[75px] xl:text-[140px] font-bold inter transition-all duration-200 ease-in-out">Better Github Classroom</h1>
        </transition>
        <div class="flex flex-start gap-[10%]">
            <transition name="fade-left-a">
                <button v-if="mounted" @click="logIn" class="rounded-full bg-[#22c9e3] shadow-lg hover:shadow-xl active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] hover:-translate-y-0.5 active:translate-y-1 ease-in-out inter font-bold text-white min-w-60 w-[30%] lg:text-4xl text-3xl py-6 flex justify-around items-center">
                    <UserCheck2 :size="48" color="white" />
                    Log In</button>
            </transition>
            <transition name="fade-left-b">
                <button v-if="mounted" @click="signUp" class="rounded-full bg-[#22c9e3] shadow-lg hover:shadow-xl active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] hover:-translate-y-0.5 active:translate-y-1 ease-in-out inter font-bold text-white min-w-60 w-[30%] lg:text-4xl text-3xl py-6 flex justify-around items-center">
                    <UserAdd2 :size="48" color="white" />
                    Sign Up</button>
            </transition>
        </div>
    </div>
</template>

<script setup lang="ts">
import { UserAdd2, UserCheck2 } from 'reicon-vue';
const mounted = ref<boolean>(false)
onMounted((() => mounted.value = true))
function logIn() {
    return navigateTo("/classes")
}

function signUp() {
    return navigateTo("/classes")
}
</script>

<style scoped>
.fade-above-enter-from,
.fade-above-leave-to {
    opacity: 0;
    translate: 0 -6%
}

.fade-above-enter-to,
.fade-above-leave-from {
    opacity: 1
}

.fade-above-enter-active,
.fade-above-leave-active {
    transition: all 600ms ease-in-out
}

.fade-left-a-enter-from,
.fade-left-a-leave-to {
    opacity: 0;
    translate: -20%
}

.fade-left-a-enter-to,
.fade-left-a-leave-from {
    opacity: 1
}

.fade-left-a-enter-active,
.fade-left-a-leave-active {
    transition: all 800ms ease-in-out
}

.fade-left-b-enter-from,
.fade-left-b-leave-to {
    opacity: 0;
    translate: -20%
}

.fade-left-b-enter-to,
.fade-left-b-leave-from {
    opacity: 1
}

.fade-left-b-enter-active,
.fade-left-b-leave-active {
    transition: all 600ms ease-in-out
}
</style>