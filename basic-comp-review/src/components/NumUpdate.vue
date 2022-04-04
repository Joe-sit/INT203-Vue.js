<script setup>
import { onUnmounted, onBeforeUnmount } from 'vue'
defineProps({
    currentNum: Number
})
onUnmounted(() => alert('on unmounted, NumUpdate Component'))
onBeforeUnmount(() => alert('on before unmounted, NumUpdate Component'))
</script>
 
<template>
    <div>current num: {{ currentNum }}</div>
</template>
 
<style>
</style>