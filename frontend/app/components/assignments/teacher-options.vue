<template>
    <div v-if="mounted" class="absolute w-[25vw] min-w-fit flex flex-col justify-start -top mt-3 left-[-60%] bg-slate-300/86 rounded-lg p-2 shadow-lg z-15">
        <button @click="deleteAssignment"
         class='text-black text-lg inter font-bold whitespace-nowrap w-full text-left flex items-center gap-2 
        transition-colors ease-in-out duration-300 p-1.5 rounded-md
        hover:bg-red-400/20 active:bg-red-400/60'>
            <Trash3 :size="24" :color="'black'"/>
            Delete Assignment
        </button>
        <button @click="$emit('edit-assignment')"
        class='text-black text-lg inter font-bold whitespace-nowrap w-full text-left flex items-center gap-2 
        transition-colors ease-in-out duration-300 p-1.5 rounded-md
        hover:bg-amber-400/20 active:bg-amber-400/60'>
            <PenCircle :size="24" :color="'black'"/>
            Edit Assignment
        </button>
        <button @click="downloadAllRepos"
        class='text-black text-lg inter font-bold whitespace-nowrap w-full text-left flex items-center gap-2 
        transition-colors ease-in-out duration-300 p-1.5 rounded-md
        hover:bg-cyan-400/20 active:bg-cyan-400/60'>
            <Download3 :size="24" :color="'black'"/>
            Download All Repositories
        </button>
    </div>
</template>

<script setup lang="ts">
import { Trash3, PenCircle, Download3 } from 'reicon-vue';
const emit = defineEmits(['edit-assignment'])
const mounted = ref<boolean>(false)
onMounted(() => mounted.value = true)

function deleteAssignment() {
    return navigateTo('/classes/1')
}

function downloadAllRepos() {

}
</script>

<style scoped>
</style>