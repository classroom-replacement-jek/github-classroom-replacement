<template>
    <div class="bg-[#262D35] h-dvh w-[vw] py-[2%] px-[5%] flex flex-col justify-around gap-[10vh]">
        <h1 class="text-[#B5FFF9] lg:text-[120px] md:text-[100px] text-[75px] xl:text-[140px] font-bold inter transition-all duration-200 ease-in-out">Better Github Classroom</h1>
        <div class="flex flex-start gap-[10%]">
            <button @click="logIn" class="rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] hover:-translate-y-0.5 active:translate-y-1 ease-in-out inter font-bold text-white min-w-60 w-[30%] lg:text-4xl text-3xl py-6 flex justify-around items-center">
                <UserCheck2 :size="48" color="white" />
                Log In</button>
            <button @click="signUp" class="rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] hover:-translate-y-0.5 active:translate-y-1 ease-in-out inter font-bold text-white min-w-60 w-[30%] lg:text-4xl text-3xl py-6 flex justify-around items-center">
                <UserAdd2 :size="48" color="white" />
                Sign Up</button>
        </div>
    </div>
</template>

<script setup lang="ts">
import { UserAdd2, UserCheck2 } from 'reicon-vue';

function logIn() {
    return navigateTo("/classes")
}

function signUp() {
    return navigateTo("/classes")
}
</script>

<style scoped>

</style>