<template>
    <div class="bg-[#0E1B38] w-full min-h-15 rounded-lg flex justify-between items-center shadow-md p-4">
        <div class="flex items-center justify-center h-[120%] aspect-square transition-colors ease-in-out duration-300
        rounded-lg hover:bg-cyan-300/20 active:bg-cyan-300/50">
            <Download3 :size="24" :color="'#22c9e3'" :weight="'Filled'"/>
        </div>
        <h6 class="inter text-white font-bold text-md w-[40%]!">Kammy Lam</h6>
        <h6 class="inter text-white font-bold text-md w-[15%]!">999 commits</h6>
        <classes-assignment-status :status="'Submitted'"></classes-assignment-status>
        <button @click="" class="relative w-fit px-4 lg:py-2 rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white text-md flex justify-center items-center hover:-translate-y-0.5 active:translate-y-px gap-2">
            <!--@click takes you to the repo-->
            <EyeOpen :size="24" :color="'white'"/>
            Open Repository
        </button>
    </div>
</template>

<script setup lang="ts">
import { EyeOpen, Download3 } from 'reicon-vue';
</script>

<style scoped>

</style>