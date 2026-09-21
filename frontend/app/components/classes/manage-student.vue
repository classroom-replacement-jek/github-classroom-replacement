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
                <h2 class="text-2xl inter text-[#262D35] font-extrabold">Manage Students</h2>
            </div>
            <div class="flex items-center justify-center text-[3rem] font-extrabold text-center w-full bg-[#262D35] text-[#22c9e3] rounded-lg py-3 shadow-lg">
                CLASS CODE: 0000-0000
            </div>
            <div class="w-full h-full overflow-y-scroll bg-[#262D35] rounded-lg shadow-lg p-2">
                <h3 class="text-xl text-white inter font-bold">Students: (34)</h3>
                <div class="flex flex-row justify-start gap-6 flex-wrap mt-2 scrollbar-thumb-[#262D35]">
                    <classes-student-card v-for="i in 34"></classes-student-card>
                </div>
            </div>
        </div>
    </transition>
</template>

<script setup lang="ts">
import { XCircle} from 'reicon-vue';
const emit = defineEmits(['close', 'create-assignment'])
const mounted = ref<boolean>(false)
onMounted(() => mounted.value = true)

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