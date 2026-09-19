<template>
    <transition name="fade-below">
        <div v-if="mounted" class="bg-slate-800/60 shadow-xl w-full h-[67vh] rounded-2xl flex flex-row gap-6 overflow-y-scroll p-[2%] scrollbar-thumb-black/0">
            <classes-course-card v-for="i in 10"></classes-course-card>
        </div>
    </transition>
</template>

<script setup lang="ts">
const mounted = ref<boolean>(false)
onMounted((() => mounted.value = true))
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
    transition: all 600ms ease-in-out
}
</style>