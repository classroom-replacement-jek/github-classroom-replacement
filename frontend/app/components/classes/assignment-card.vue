<template>
    <div class="bg-[#0E1B38] w-full min-h-15 rounded-lg flex justify-between items-center shadow-md p-4">
        <h6 class="inter text-white font-bold text-md w-[40%]!">Assignment Name</h6>
        <h6 class="inter text-white font-bold text-md w-[15%]!">Due 00/00/0000</h6>
        <classes-assignment-status :status="'Submitted'" v-if="true"></classes-assignment-status>
        <!--the v-if here is for student-->
        <button @click="navigateTo('/classes/1/assignments/1')" class="relative w-fit px-4 lg:py-2 rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white text-md flex justify-center items-center hover:-translate-y-0.5 active:translate-y-px gap-2">
            <EyeOpen :size="24" :color="'white'"/>
            View
        </button>
    </div>
</template>

<script setup lang="ts">
import { EyeOpen } from 'reicon-vue';
</script>

<style scoped>

</style>