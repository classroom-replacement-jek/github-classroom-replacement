<template>
    <div>
        <transition name="fade-above">
            <div class="sticky top-0 w-full h-[7vh]">
                hi
            </div>
        </transition>
        <slot></slot>
    </div>
</template>

<script setup lang="ts">

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
    transition: all 300ms ease-in-out
}
</style>