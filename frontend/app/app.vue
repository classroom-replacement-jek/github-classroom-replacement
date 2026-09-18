<template>
  <nuxt-layout :name="layoutName">
    <nuxt-page></nuxt-page>
  </nuxt-layout>
</template>

<script setup lang="ts">
const layoutName = computed(() => {
  if(useRoute().path === '/') return 'default'
  else return 'user-bar'
})
</script>