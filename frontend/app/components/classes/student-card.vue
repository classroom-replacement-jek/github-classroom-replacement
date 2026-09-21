<template>
    <div class="w-fit h-fit bg-[#22c9e3] p-2 rounded-lg flex flex-col gap-2 min-w-[23.5%]">
        <h4 class="inter font-bold text-black">Edward Mercado</h4>
        <button class="flex items-center justify-center gap-2 px-1 bg-white w-full rounded-md text-black font-bold transition-all ease-in-out duration-300
        hover:bg-red-100 active:bg-red-300 shadow-sm hover:shadow-lg active:shadow-none hover:-translate-y-px active:translate-y-px">
            Kick <ArrowDoorOut :size="24"></ArrowDoorOut>
        </button>
    </div>
</template>

<script setup lang="ts">
import { ArrowDoorOut } from 'reicon-vue'
</script>

<style scoped>

</style>