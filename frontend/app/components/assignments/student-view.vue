<template>
    <div class="bg-slate-800/60 shadow-xl w-full h-[67vh] rounded-2xl flex flex-col justify-between gap-6 p-[2%]">
        <h3 class="inter text-white font-bold text-2xl h-[70%]">Sample Assignment Description, something like... In this project you will have to leverage a while loop in order to create a random number guessing game. The program should generate a random number, and then ask you to guess until you correctly guess what it is. It should give you hints (ex. "Higher" or "Lower") until it finally tells you "Correct!".</h3>
        <button v-if="false" @click="" class="relative w-full px-10 py-5 rounded-full bg-[#22c9e3] text-3xl lg:text-4xl shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white text-md flex justify-center items-center hover:-translate-y-0.5 active:translate-y-px gap-2">
            <!--this boolean is if the assignment is marked as 'not started'-->
            Accept this Assignment</button>
        <div v-else class="flex flex-row justify-between gap-[5%] h-[15%]">
            <button v-if="true" @click="" class="relative w-[80%] rounded-full bg-[#22c9e3] text-2xl shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white text-md flex justify-center items-center hover:-translate-y-0.5 active:translate-y-px gap-2">
            <!--this boolean is if the assignment is marked as 'not started'-->
            Open Your Repository</button>
            <button v-if="true" @click="" class="relative w-[35%] px-10 py-5 rounded-full bg-[#22c9e3] text-2xl shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white text-md flex justify-center items-center hover:-translate-y-0.5 active:translate-y-px gap-2">
            <!--this boolean is if the assignment is marked as 'not started'-->
            Mark as Done</button>
        </div>
    </div>
</template>

<script setup lang="ts">

</script>

<style scoped>

</style>