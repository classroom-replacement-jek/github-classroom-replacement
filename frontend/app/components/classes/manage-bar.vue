<template>
    <transition name="fade-above">
        <div v-if="mounted" class="h-[7vh] w-full mt-[15vh] flex justify-start items-center gap-6">
            <div
                class="relative flex h-[7vh]">
                <button class="relative h-full! p-0 aspect-square rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white lg:text-4xl text-3xl flex justify-center items-center" @click="newClassModal = !newClassModal">
                    <Add :size="36" class="transition-all duration-300 ease-in-out" :class="newClassModal ? '-rotate-45' : ''"></Add>
                </button>
                <transition name="new-modal">
                    <classes-new-modal v-if="newClassModal"></classes-new-modal>
                </transition>
            </div>
            <h3 class="text-2xl inter text-white font-extrabold">Your Classes</h3>
        </div>
    </transition>
</template>

<script setup lang="ts">
import { Add } from 'reicon-vue';

const mounted = ref<boolean>(false)
const newClassModal = ref<boolean>(false)
onMounted((() => mounted.value = true))
</script>

<style scoped>
.fade-above-enter-from,
.fade-above-leave-to {
    opacity: 0;
    translate: 0 -60%
}

.fade-above-enter-to,
.fade-above-leave-from {
    opacity: 1
}

.fade-above-enter-active,
.fade-above-leave-active {
    transition: all 600ms ease-in-out
}

.new-modal-enter-from,
.new-modal-leave-to {
    opacity: 0
}

.new-modal-leave-from,
.new-modal-enter-to {
    opacity: 1
}

.new-modal-enter-active,
.new-modal-leave-active {
    transition: 300ms
}
</style>