<template>
    <transition name="fade">
        <div v-if="mounted" @click="closeModal" class="bg-slate-900/60 z-0 w-screen h-dvh fixed left-0 top-0">

        </div>
    </transition>
    <transition name="fade-below">
        <div v-if="mounted"
            class="fixed flex flex-col justify-start items-start top-[3vh] h-[94vh] left-[3vw] w-[94vw] z-12 bg-slate-300/86 rounded-2xl p-[2%] gap-10">
            <div class="w-full flex flex-row justify-start items-center gap-4">
                <div @click="closeModal" class="w-12 aspect-square flex items-center justify-center rounded-full
                transition-colors ease-in-out duration-300 hover:bg-sky-100 active:bg-sky-300">
                    <XCircle class="block" :size="38" color="#262D35" />
                </div>
                <h2 class="text-2xl inter text-[#262D35] font-extrabold">Create New Assignment</h2>
            </div>
            <div class="flex flex-row justify-start items-center w-full gap-4">
                <p class="text-2xl inter text-[#262D35] font-extrabold w-[25%]">Assignment Name</p>
                <input type="text" v-model="assignmentDetails.name" placeholder="Enter Assignment Name..." class="w-[60%] py-2 px-4 rounded-lg bg-[#262D35]/60 focus:bg-[#262D35] focus:outline-none placeholder-cyan-300/60 transition-colors ease-in-out duration-300 text-white inter font-bold text-lg">
            </div>
            <div class="flex flex-row justify-start items-center w-full gap-4">
                <p class="text-2xl inter text-[#262D35] font-extrabold w-[25%]">Due Date</p>
                <input type="date" v-model="assignmentDetails.dueDate" class="w-[60%] py-2 px-4 rounded-lg bg-[#262D35]/60 focus:bg-[#262D35] focus:outline-none transition-colors ease-in-out duration-300 text-cyan-300/60 inter font-bold text-lg [&::-webkit-datetime-edit]:text-cyan-300/60">
            </div>
            <div class="flex flex-row justify-start items-center w-full gap-4">
                <p class="text-2xl inter text-[#262D35] font-extrabold w-[25%]">Template Repository</p>
                <input type="file" webkitdirectory multiple class="flex gap-2 w-[60%] py-2 px-4 rounded-lg bg-[#262D35]/60 focus:bg-[#262D35] focus:outline-none transition-colors ease-in-out duration-300 text-cyan-300/60 inter font-bold text-lg">
                <!-- make sure you can convert this file upload into data we can put on the db-->
            </div>
            <div class="flex flex-col justify-start items-start w-full gap-4 h-[30%]">
                <p class="text-2xl inter text-[#262D35] font-extrabold w-[25%]">Assignment Description</p>
                <textarea rows="5" v-model="assignmentDetails.desc" placeholder="Enter Assignment Description..." class="w-full py-2 px-4 rounded-lg bg-[#262D35]/60 focus:bg-[#262D35] focus:outline-none placeholder-cyan-300/60 transition-colors ease-in-out duration-300 text-white inter flex items-start justify-start font-bold text-lg h-full"> </textarea>
            </div>
            <button class="rounded-full bg-[#22c9e3] shadow-lg hover:shadow-xl active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] hover:-translate-y-0.5 active:translate-y-1 ease-in-out inter font-bold text-white lg:text-2xl text-xl items-center w-[50%] py-2 justify-center flex gap-3">
                <AddSquare :size="32" />
                Create Assignment
            </button>
        </div>
    </transition>
</template>

<script setup lang="ts">
import { XCircle, AddSquare } from 'reicon-vue';
const emit = defineEmits(['close'])
const mounted = ref<boolean>(false)
onMounted(() => mounted.value = true)

let assignmentDetails = {
    name: null as string | null,
    dueDate: null as Date | null,
    desc: null as string | null,
}

async function closeModal() {
    mounted.value = false
    setTimeout(() => emit('close'), 300)
}
</script>

<style scoped>
.fade-below-enter-from,
.fade-below-leave-to {
    opacity: 0;
    translate: 0 6%
}

.fade-below-enter-to,
.fade-below-leave-from {
    opacity: 1
}

.fade-below-enter-active,
.fade-below-leave-active {
    transition: all 300ms ease-in-out
}


.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity 200ms ease-in-out;
}

.fade-enter-to,
.fade-leave-from {
    opacity: 1;
}
</style>