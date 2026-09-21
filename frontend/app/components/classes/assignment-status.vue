<template>
    <div
    class="w-fit px-4 py-1 rounded-full border-2 inter font-bold" :class="statusClasses">
        {{ prop.status }}
    </div>
</template>

<script setup lang="ts">
const prop = defineProps<{
    status: ('Not Started' | "In Progress" | "Submitted")
}>()

const statusClasses = computed(() => {
    const allClasses = {
        "Not Started": ['border-red-400', 'text-red-400'],
        "In Progress": ['border-yellow-300', 'text-yellow-300'],
        "Submitted": ['border-cyan-300', 'text-cyan-300'],
    }
    return allClasses[prop.status] ?? ''
})
</script>

<style scoped>

</style>