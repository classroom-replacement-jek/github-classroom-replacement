<template>
    <transition name="fade-above">
        <div v-if="mounted" class="h-[7vh] w-full mt-[15vh] flex justify-between items-center gap-6">
            <div class="flex h-full gap-4 items-center justify-start ">
                <button class="relative h-full! p-0 aspect-square rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white lg:text-4xl text-3xl flex justify-center items-center" @click="navigateTo('/classes')">
                    <BackSquare :size="32" :color="'white'"/>
                </button>
                <div class="h-full relative">
                    <button @click="viewingOptions = !viewingOptions" class="relative h-full! p-0 aspect-square rounded-full bg-[#22c9e3] shadow-sm hover:shadow-lg active:shadow-none transition-all duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white lg:text-4xl text-3xl flex justify-center items-center">
                        <Menu :size="32" :color="'white'" />
                    </button>
                    <span></span>
                    <transition name="fade-above">
                        <classes-class-options v-if="viewingOptions"
                        @view-students="viewingOptions = false; viewingStudents = true"
                        ></classes-class-options>
                    </transition>
                </div>
                <h3 class="text-2xl inter text-white font-extrabold z-2">APCSP Pd 6 <span class="italic">(with Teacher Name)</span></h3>
            </div>
            <button @click="showAssignmentCreation = true" v-if="false" class="relative h-full! p-0 rounded-full bg-[#22c9e3] transition-all text-lg duration-300 hover:bg-[#0cbecf] active:bg-[#07a5ad] ease-in-out inter font-bold text-white px-4 flex justify-center items-center shadow-sm hover:shadow-lg active:shadow-none hover:-translate-y-1 active:translate-y-0.5 gap-2">
                <!--the 'true' is gonna be if the user is the teacher of the class-->
                <AddCircle :size="32" :color="'white'"/>
                Create New Assignment
            </button>
        </div>
    </transition>
    <classes-manage-student @close="viewingStudents = false" v-if="viewingStudents"></classes-manage-student>
    <classes-assignment-creation 
    @close="showAssignmentCreation = false" @create-assignment="(assignmentDetails) => {}"
    v-if="showAssignmentCreation"></classes-assignment-creation>
</template>

<script setup lang="ts">
import { BackSquare, Menu, AddCircle } from 'reicon-vue';
const mounted = ref<boolean>(false)
const viewingOptions = ref<boolean>(false)
const viewingStudents = ref<boolean>(false)
onMounted((() => mounted.value = true))
const showAssignmentCreation = ref<boolean>(false)
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
</style>