<script setup>
import { onMounted } from 'vue'
import { RouterView } from 'vue-router'

onMounted(() => {
    localStorage.setItem('order', JSON.stringify({}))
    localStorage.setItem('orderLength', 0)
})
</script>

<template>
    <RouterView />
</template>

<style scoped></style>