<template>
    <div class="absolute left-[130%] w-[45vw] top-[-60%] h-[220%] flex flex-col items-center justify-between">
        <transition name="fade-left-up">
            <div v-if="mounted" class="w-full h-[45%] bg-[#22c9e3]/70 rounded-lg text-lg flex items-center justify-between inter px-[2%] py-2 gap-2">
                <input v-model="inputClassCode" type="text" class="w-[80%] bg-[#262D35]/60 focus:bg-[#262D35] transition-all duration-300 ease-in-out shadow-sm focus:shadow-lg h-full rounded-lg focus:outline-none placeholder-sky-200 inter font-bold text-white px-[3%]" placeholder="Enter Class Code (for students)">
                <button class="bg-white p-2 rounded-lg text-[#262D35] h-full inter md:text-md text-xs font-bold max-h-full w-[30%] hover:bg-cyan-100 active:bg-cyan-200 transition-all duration-300 
                ease-in-out hover:-translate-x-0.5 active:translate-x-px shadow-sm hover:shadow-lg active:shadow-none">Join Class</button>
            </div>
        </transition>

        <transition name="fade-left-down">
            <div v-if="mounted" class="w-full h-[45%] bg-[#22c9e3]/70 rounded-lg text-lg flex items-center justify-between inter px-[2%] py-2 gap-2">
                <input v-model="inputClassName" type="text" class="w-[80%] bg-[#262D35]/60 focus:bg-[#262D35] transition-all duration-300 ease-in-out shadow-sm focus:shadow-lg h-full rounded-lg focus:outline-none placeholder-sky-200 inter font-bold text-white px-[3%]" placeholder="Enter Class Name (for teachers)">
                <button class="bg-white p-2 rounded-lg text-[#262D35] h-full inter md:text-md text-xs font-bold max-h-full w-[30%] hover:bg-cyan-100 active:bg-cyan-200 transition-all duration-300 
                ease-in-out hover:-translate-x-0.5 active:translate-x-px shadow-sm hover:shadow-lg active:shadow-none">Create Class</button>
            </div>
        </transition>
    </div>
</template>

<script setup lang="ts">
const mounted = ref(false)
onMounted(() => mounted.value = true)

const inputClassCode = ref<string>()
const inputClassName = ref<string>()

</script>

<style scoped>
.fade-left-up-enter-from,
.fade-left-up-leave-to,
.fade-left-down-enter-from,
.fade-left-down-leave-to {
    opacity: 0;
}

.fade-left-up-enter-from,
.fade-left-up-leave-to {
    translate: -30% 10%;
}

.fade-left-down-enter-from,
.fade-left-down-leave-to {
    translate: -30% -10%;
}

.fade-left-up-enter-active,
.fade-left-up-leave-active,
.fade-left-down-enter-active,
.fade-left-down-leave-active {
    transition: all 600ms ease-in-out;
}

.fade-left-up-enter-to,
.fade-left-up-leave-from,
.fade-left-down-enter-to,
.fade-left-down-leave-from {
    opacity: 1;
    translate: 0 0;
}
</style>