<template>
    <div v-if="mounted" class="absolute w-[25vw] min-w-fit flex flex-col justify-start -top mt-3 left-[-60%] bg-slate-300/86 rounded-lg p-2 shadow-lg z-15">
        <button v-if="isTeacher" @click="$emit('view-students')"
        class='text-black text-lg inter font-bold whitespace-nowrap w-full text-left flex items-center gap-2 
        transition-colors ease-in-out duration-300 p-1.5 rounded-md
        hover:bg-cyan-400/20 active:bg-cyan-400/60'>
            <User2 :size="24" :color="'black'"/>
            Manage Students
        </button>
        <button v-if="isTeacher" @click="deleteCount++"
         class='text-black text-lg inter font-bold whitespace-nowrap w-full text-left flex items-center gap-2 
        transition-colors ease-in-out duration-300 p-1.5 rounded-md
        hover:bg-red-400/20 active:bg-red-400/60'>
            <Trash3 :size="24" :color="'black'"/>
            {{ deleteCount !== 1 ? 'Delete Class' : 'Are you sure?' }}
        </button>
        <button v-if="!isTeacher" @click="navigateTo('/classes')"
        class='text-black text-lg inter font-bold whitespace-nowrap w-full text-left flex items-center gap-2 
        transition-colors ease-in-out duration-300 p-1.5 rounded-md
        hover:bg-red-400/20 active:bg-red-400/60'>
            <ArrowDoorOut :size="24" :color="'black'"/>
            Leave Class
        </button>
    </div>
</template>

<script setup lang="ts">
import { Trash3, User2, ArrowDoorOut } from 'reicon-vue';
const emit = defineEmits(['view-students'])
const isTeacher = ref<boolean>(false)
const deleteCount = ref<number>(0)

let timeout = 0

watch(() => deleteCount.value, () => {
    if(deleteCount.value === 2) {
        deleteClass()
        clearTimeout(timeout)
    } else {
        let timeout = setTimeout(() => {
            deleteCount.value = 0
        }, 2000)
    }
})

const mounted = ref<boolean>(false)
onMounted(() => mounted.value = true)

function deleteClass() {
    return navigateTo('/classes')
}
</script>

<style scoped>
</style>